<template>
  <div id="cart">
    <SfSidebar
      v-e2e="'sidebar-cart'"
      :visible="isCartSidebarOpen"
      class="sf-sidebar--right "
      :title="'Shopping cart ('+products.length+')'"
      @close="toggleCartSidebar"
      
    >
       <template #content-top>
         <div class="return-replace-text">
          <div class="return-replace-text-info">
            <span>
              <template>
                <span class="sf-icon color-black size-md">
                  <svg class="sf-icon-path" viewBox="0 -6 24 28" preserveAspectRatio="none">
                    <path
                      d="M21.998 7.324L17.845 2H7.154L3 7.324V22h19l-.002-14.676zm-1.643-.357h-7.31V3.103h4.284l3.026 3.864zM7.668 3.103h4.283v3.864h-7.31l3.027-3.864zM4.062 20.895V8.037h16.873v12.858H4.063zm8.436-10.486l2.802 2.824-.772.78-1.514-1.527v5.78h-1.063v-5.78l-1.513 1.526-.772-.779 2.832-2.824z"
                      fill="var(--icon-color)"
                    />
                  </svg>
                </span>
              
              </template> 
                
            </span>
            <span class="bold"> Free shipping & 30 day return &nbsp</span>
              <a href="javascript:void(0)" >Learn More</a>
            </div>
          </div>
      </template>
   
      <transition name="sf-fade" mode="out-in">
        <div v-if="totalItems" key="my-cart" class="my-cart">
          <div class="collected-product-list">
            <transition-group name="sf-fade" tag="div">
              <SfCollectedProduct
                v-for="(product,i) in products"
                :key="cartGetters.getItemSku(product)"
                :image="cartGetters.getItemImage(product)"
                :imageWidth="60"
                :imageHeight="80"
                :title="cartGetters.getItemName(product)"
                :regular-price="$n(cartGetters.getItemPrice(product).regular, 'currency')"
                :special-price="cartGetters.getItemPrice(product).special && $n(cartGetters.getItemPrice(product).special, 'currency')"
                :stock="99999"
                @click:remove="removeItem({ product })"
              >
                <template #configuration>
                  <div class="collected-product__properties">
                    <!-- <SfProperty
                      v-for="(attribute, key) in cartGetters.getItemAttributes(product, ['color', 'size'])"
                      :key="key"
                      :name="key"
                      :value="attribute"
                    /> -->
                  </div>
                </template>
                <template #title>
                   <div class="collected-product__title_price">
                     <div class="collected-product_title">
                       {{cartGetters.getItemName(product)}}
                     </div>
                     <div class="collected-product_price">
                        {{$n(cartGetters.getItemPrice(product).regular, 'currency')}}

                     </div>
                   </div>
               
                </template>
                <template #price>
                 <SfProperty
                      name="qty"
                      class="sf-property--full-width color-light sf-property--large my-cart__total-price"
                    >
                      <template #name>
                        <div class=" sm-text light-text">
                          qty
                           <SfButton
                            class=" color-danger  btn-remove_product"
                            @click="removeItem({ product })"
                          >Remove</SfButton
                          >
                        </div>
                        <div>
                       
                        </div>
                    
                    </template>
                    <template #value>
                      <SfQuantitySelector
                      :disabled="loading"
                      :qty="cartGetters.getItemQty(product)"
                      class="sf-collected-product__quantity-selector"
                      @input="updateItemQty({ product, quantity: $event })"
                    />
                    </template>
                </SfProperty>
                 <SfProperty
                      name="color"
                      class="sf-property--full-width color-light sf-property--large my-cart__total-price"
                    >
                      <template #name>
                        <div class=" sm-text light-text">
                          Color
                          {{selectedColor[cartGetters.getItemSku(product)]}}
                          
                        </div>
                    </template>
                    <template #value>
                      <div class="sf-quantity-selector sf-collected-product__quantity-selector space-around">
                        
                        <div class="form-check" v-for="(color,index) in productColors" :key="index" >
                          <CustomRadio :colorname="color.color_name" :value="color.color_code" :name="'radio'+i" :color="color.color_code" @onColorChanged="selectColor($event,cartGetters.getItemSku(product))" :isSelected="color.isSelected"/>
                          <!-- <input class="form-check-input custom_radio" type="radio"   name="colors" :id="index+color.color_name" :value="color.color_code">
                          <label class="form-check-label custom_radio-label" :for="index+color.color_name">
                          </label> -->
                        </div>
                      </div>
                    </template>
                </SfProperty>
              </template>
                <template #input>
                  <div>
                  </div>
                </template>
              </SfCollectedProduct>
            </transition-group>
          </div>
        </div>
        <div v-else key="empty-cart" class="empty-cart">
          <div class="empty-cart__banner">
            <SfImage
              alt="Empty bag"
              class="empty-cart__image"
              src="/icons/empty-cart.svg"
            />
            <SfHeading
              title="Your cart is empty"
              :level="2"
              class="empty-cart__heading"
              description="Looks like you haven’t added any items to the bag yet. Start
              shopping to fill it in."
            />
          </div>
        </div>
      </transition>
      <template #content-bottom>
        <transition name="sf-fade">
          <div v-if="totalItems">
            <div class="smtitle">Order Summary</div>
            <SfProperty
              name="Subtotal price"
              class="sf-property--full-width color-light sf-property--large my-cart__total-price"
            >
              <template #value>
                <SfPrice
                  :regular="$n(totals.subtotal, 'currency')"
                  :special="(totals.special !== totals.subtotal) ? $n(totals.special, 'currency') : 0"
                />
              </template>
            </SfProperty>
             <SfProperty
              name="Shipping"
              class="sf-property--full-width color-light sf-property--large my-cart__total-price"
            >
              <template #value>
                <SfPrice
                  regular="Free"
                />
              </template>
            </SfProperty>
             <SfProperty
              name="Promo"
              class="sf-property--full-width color-light sf-property--large my-cart__total-price"
            >
              <template #value>
                <SfPrice
                  regular="$0"
                />
              </template>
            </SfProperty>
             <SfProperty
              name="Est.Tax & Fees"
              class="sf-property--full-width color-light sf-property--large my-cart__total-price"
            >
              <template #value>
                <SfPrice
                  regular="-"
                />
              </template>
            </SfProperty>
             <SfProperty
              name="Promo code"
              class="sf-property--full-width color-light sf-property--large my-cart__total-price"
            >
              <template #value>
                <a href="javascript:void(0)">Add promo code</a>
              </template>
            </SfProperty>
            <nuxt-link :to="localePath({ name: 'shipping' })">
              <SfButton
                v-e2e="'go-to-checkout-btn'"
                class="sf-button--full-width color-secondary checkout-btn"
                @click="toggleCartSidebar"
              >
               <div class="dispIn"> {{ $t('Go to checkout') }}</div>
               <div class="dispIn">{{$n(totals.subtotal, 'currency')}}</div>
              </SfButton>
            </nuxt-link>
          </div>
          <div v-else>
            <SfButton
              class="sf-button--full-width color-primary"
              @click="toggleCartSidebar"
            >{{ $t('Go back shopping') }}</SfButton
            >
          </div>
        </transition>
      </template>
    </SfSidebar>
  </div>
</template>
<script>
import CustomRadio from './CustomRadio.vue'
import {
  SfSidebar,
  SfHeading,
  SfButton,
  SfIcon,
  SfProperty,
  SfPrice,
  SfRadio,
  SfCollectedProduct,
  SfImage,
  SfQuantitySelector
} from '@storefront-ui/vue';
import { ref,computed } from '@vue/composition-api';
import { useCart, useUser, cartGetters } from '@vue-storefront/commercetools';
import { useUiState } from '~/composables';
export default {
  name: 'Cart',
  components: {
    SfSidebar,
    SfButton,
    SfHeading,
    SfIcon,
    SfProperty,
    SfRadio,
    SfPrice,
    SfCollectedProduct,
    SfImage,
    CustomRadio,
    SfQuantitySelector
  },
  setup() {
    const { isCartSidebarOpen, toggleCartSidebar } = useUiState();
    const { cart, removeItem, updateItemQty, load: loadCart, loading } = useCart();
    const { isAuthenticated } = useUser();
    const products = computed(() => cartGetters.getItems(cart.value));
    const totals = computed(() => cartGetters.getTotals(cart.value));
    const totalItems = computed(() => cartGetters.getTotalItems(cart.value));
    let selectedColor =ref({})
    const productColors =[{
      "color_name":"Martian Red",
      "color_code":"#da3838",
      "isSelected":true
    },
    {
      "color_name":"Blue",
      "color_code":"#0000ff",
      "isSelected":false
      

    }]
    loadCart();

    return {
      loading,
      isAuthenticated,
      products,
      removeItem,
      updateItemQty,
      isCartSidebarOpen,
      toggleCartSidebar,
      totals,
      totalItems,
      productColors,
      selectedColor,
      cartGetters
    };
  },
  methods:{
    selectColor(val,key){
      console.log('selected'+val)
      this.selectedColor[key] =val
    }
  }

};
</script>

<style lang="scss" >
#cart {
  --sidebar-z-index: 3;
  --overlay-z-index: 3;
  @include for-desktop {
    & > * {
      --sidebar-bottom-padding: var(--spacer-base);
      --sidebar-content-padding: var(--spacer-base);
    }
  }
  .sf-sidebar{
  &__top{
    padding:0px;
    .sf-heading__title{
    padding: 15px;
  }
  }
 
}
.sf-sidebar__content{
   padding: 0 0 var(--spacer-base) 0;

}
.btn-remove_product{
  background: none;
    padding: 1px;
    font-size: x-small;
    font-weight: var(--font-weight--bold);
    text-decoration: underline;
    color: var( --c-danger);
}
.light-text{
   color: var(--property-color, var(--c-light-primary));
}
.sm-text{
      font-size: var(--font-size--xs);
    font-weight: var(--font-weight--bold);
}
.sf-property--large{
      color: var(--property-color, var(--c-light-primary));
       a{
        text-decoration: underline;
        font-size: var(--font-size--xs);
        font-weight:var(--font-weight--bold);
        color: blue;
      }
  --property-name-font-size: var(--font-size--xs);
  --property-name-color:#d2d1d0;
    --property-name-font-weight: var(--font-weight--medium);
    .sf-price {
      --price-regular-font-size: var(--font-size--xs);
        --price-regular-font-weight: var(--font-weight--bold);
    }
    
}

 .checkout-btn{
        justify-content: space-between;
        border-radius: 30px;
  }
.cart-summary {
  margin-top: var(--spacer-xl);
}
.smtitle{
  font-weight:var(--font-weight--medium);
  font-size: var(--font-size--lg);
  margin-bottom:var(--spacer-sm);
}
.sf-heading__title  {
  margin-bottom: var(--spacer-xs);
 --heading-title-font-weight:var(--font-weight--large);
 
}
.return-replace-text{
    padding: 10px;
    margin-top: 10px;
    background: #d4cbcb57;
    font-size: 12px;
    text-align: center;
    font-weight: 600;
    .return-replace-text-info{
      display: inline-block;
      a{
        text-decoration: underline;
      }
      .bold{
        font-size: 13px;
        font-weight: 800;
      }
      .sf-icon{
        display: inline-block;
      }
    }
    
}

.my-cart {
  flex: 1;
  display: flex;
  flex-direction: column;
  &__total-items {
    margin: 0;
  }
  &__total-price {
    --price-font-size: var(--font-size--xl);
    --price-font-weight: var(--font-weight--medium);
    margin: 0 0 var(--spacer-xs) 0;
    align-items: center;
  
  }
  .collected-product__title_price{
        display: flex;
    /* align-items: unset; */
    justify-content: space-between;
    .collected-product_price{
      font-weight: var(--font-weight--bold);
    }
     .collected-product_title{
      font-weight: var(--font-weight--bold);
    }
  }
  .space-around{
      justify-content: space-between;
  }
  .custom_radio{
    width: 2rem;
    height: 1.5rem;
  }
  .sf-collected-product {
     --collected-product-width: 95%;
    .sf-collected-product__aside {
      flex: 0 0 3.75rem;
    }
  }
  .sf-collected-product__quantity-selector {
    --quantity-selector-background: none;
    .sf-quantity-selector__button {
     border-radius: 16px;
          width: 90%;
          border: 1px solid grey;
          --button-height: 70%;
        --button-font-size: var(--font-size--xl);
        --button-font-weight: var(--font-weight--medium);
         &:focus {
              --button-background:#dcd5d5;;
         
          }

    }
    .sf-quantity-selector__input {
    --input-font-weight: var(--font-weight--medium);
    }
  }   
}
.empty-cart {
  --heading-description-margin: 0 0 var(--spacer-xl) 0;
  --heading-title-margin: 0 0 var(--spacer-xl) 0;
  --heading-title-color: var(--c-primary);
  --heading-title-font-weight: var(--font-weight--semibold);
  display: flex;
  flex: 1;
  align-items: center;
  flex-direction: column;
  &__banner {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    flex: 1;
  }
  &__heading {
    padding: 0 var(--spacer-base);
  }
  &__image {
    --image-width: 16rem;
    margin: 0 0 var(--spacer-2xl) 7.5rem;
  }
  @include for-desktop {
    --heading-title-font-size: var(--font-size--xl);
    --heading-title-margin: 0 0 var(--spacer-sm) 0;
  }
}
.collected-product-list {
  flex: 1;
 
}
.collected-product {
  margin: 0 0 var(--spacer-sm) 0;
  &__properties {
    margin: var(--spacer-xs) 0 0 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
    flex: 2;
    &:first-child {
      margin-bottom: 8px;
    }
  }
  &__actions {
    transition: opacity 150ms ease-in-out;
  }
  &__save,
  &__compare {
    --button-padding: 0;
    &:focus {
      --cp-save-opacity: 1;
      --cp-compare-opacity: 1;
    }
  }
  &__save {
    opacity: var(--cp-save-opacity, 0);
  }
  &__compare {
    opacity: var(--cp-compare-opacity, 0);
  }
  &:hover {
    --cp-save-opacity: 1;
    --cp-compare-opacity: 1;
    @include for-desktop {
      .collected-product__properties {
        display: none;
      }
    }
  }
}
}

</style>
