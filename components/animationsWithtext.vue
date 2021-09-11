<template>
  <SfSection title-heading="" subtitle-heading="" class="title">
   <SfHeading title="Additional highlights" :level="2" class="h2_miko3"/>
   <div class="bannerImg">
          <div class="">
             <div class="animations_container_mob">
                <div :class="customClasses['icon-1']">
                    <div  v-if="header =='Study budy'">
                      <img src="/icons/images/playMiko3.png"  class="img"/>
                    </div>
                    <div class="rollIcons"  v-else-if="header=='Integrated learning'">
                        <img src="/icons/star 43.svg" alt="img1" />
                    </div>
                    <div class="rollIcons"  v-else>
                        <img src="/icons/star 43.svg" alt="img1" />
                    </div>
                </div>
                <div :class="customClasses['icon-2']">
                  <div class="rollIcons" v-if="header =='Integrated learning'">
                    <img src="/icons/Polygon 5.svg" alt="img2" />
                  </div>
                  <div class="rollIcons" v-else-if="header=='Study budy'">
                    <img src="/icons/Polygon 5.svg" alt="img2" />
                  </div>
                  <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
                    <img src="/icons/Polygon 5.svg" alt="img2" />
                  </div>
                </div>
                <div :class="customClasses['icon-3']">
                  <div class="">
                    <img src="/icons/Ellipse 75.svg" alt="img3" />
                  </div>
                </div>
                <div :class="customClasses['icon-4']">
                  <div id="triangle-up" v-if="header =='Integrated learning'">
                    <img src="/icons/images/triangle.png" alt="study budy" />
                  </div>
                
                  <div class="" v-else>
                    <img src="/icons/Polygon 7.svg" alt="img4" />
                  </div>
                
                </div>
                <div :class="customClasses['icon-5']">
                  <div class="" v-if="header =='Screentime evolved'">
                    <img src="/icons/images/studyround.png" alt="study with miko2" />
                  </div>
                  <div class="" v-else>
                    <img src="/icons/Rectangle 261.svg" alt="img5" />
                  </div>
                  
                </div>
                <div :class="customClasses['icon-6']">
                  <div class="">
                    <img src="/icons/Rectangle 12.svg" alt="img7" />
                  </div>
                </div>
                <div :class="customClasses['icon-7']">
                  <div class="rollIcons" v-if="header =='Integrated learning'">
                    <img src="/icons/star 42.svg" alt="study" />
                  </div>
                  <div class="rollIcons" v-else-if="header=='Study budy'">
                  <img src="/icons/star 42.svg" alt="study" />
                  </div>
                  <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
                  <img src="/icons/star 42.svg" alt="study" />
                  </div>
                </div>
                <div :class="customClasses['icon-8']">
                  <div class="rollIcons" v-if="header =='Integrated learning'">
                    <img src="/icons/union.svg" alt="study" />
                  </div>
                  <div class="rollIcons" v-else-if="header=='Study budy'">
                      <img src="/icons/union.svg" alt="study" />
                  </div>
                  <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
                      <img src="/icons/union.svg" alt="study" />
                  </div>
                </div>
          
              </div>
          </div>
    </div>
    <div class="grid ">
      
      <div class="grid__row">
         
        
        <div class="grid__col">
          <SfAccordion transition="sf-expand" :showChevron="false" ref="acc">
            <SfAccordionItem header="Study budy" class="miko3_acrodianhead" >
                <SfList>
                  By better understanding a kid’s developmental phases Miko can help kids accelerate learning and increase intelligence.
                </SfList>
              </SfAccordionItem>
            <SfAccordionItem header="Screentime evolved" key="Screentime evolved" class="miko3_acrodianhead" >
                <SfList>
                  By better understanding a kid’s developmental phases Miko can help kids accelerate learning and increase intelligence.
                </SfList>
              </SfAccordionItem>
              <SfAccordionItem header="Integrated learning" class="miko3_acrodianhead" key="Integrated learning">
                <SfList>
                  By better understanding a kid’s developmental phases Miko can help kids accelerate learning and increase intelligence.
                </SfList>
              </SfAccordionItem>
          </SfAccordion>
        </div>  
      </div>
      <div class="grid__row">
        <div class="grid__col">
          <div class="animations_container">
            
          
            <div :class="customClasses['icon-1']">
                <div id=""  v-if="header =='Study budy'">
                  <img src="/icons/images/playMiko3.png"  class="img"/>
                </div>
                <div class="rollIcons"  v-else-if="header=='Integrated learning'">
                    <img src="/icons/star 43.svg" alt="img1" />
                </div>
                <div class="rollIcons"  v-else>
                    <img src="/icons/star 43.svg" alt="img1" />
                </div>
            </div>
            <div :class="customClasses['icon-2']">
              <div class="rollIcons" v-if="header =='Integrated learning'">
                <img src="/icons/Polygon 5.svg" alt="img2" />
              </div>
              <div class="rollIcons" v-else-if="header=='Study budy'">
                <img src="/icons/Polygon 5.svg" alt="img2" />
              </div>
               <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
                <img src="/icons/Polygon 5.svg" alt="img2" />
              </div>
            </div>
            <div :class="customClasses['icon-3']">
              <div class="">
                <img src="/icons/Ellipse 75.svg" alt="img3" />
              </div>
            </div>
            <div :class="customClasses['icon-4']">
               <div id="triangle-up" v-if="header =='Integrated learning'">
                <img src="/icons/images/triangle.png" alt="study budy" />
              </div>
            
              <div class="" v-else>
                <img src="/icons/Polygon 7.svg" alt="img4" />
              </div>
             
            </div>
            <div :class="customClasses['icon-5']">
              <div class="" v-if="header =='Screentime evolved'">
                <img src="/icons/images/studyround.png" alt="study with miko2" />
              </div>
              <div class="" v-else>
                <img src="/icons/Rectangle 261.svg" alt="img5" />
              </div>
              
            </div>
            <div :class="customClasses['icon-6']">
              <div class="">
                <img src="/icons/Rectangle 12.svg" alt="img7" />
              </div>
            </div>
            <div :class="customClasses['icon-7']">
               <div class="rollIcons" v-if="header =='Integrated learning'">
                <img src="/icons/star 42.svg" alt="study" />
              </div>
               <div class="rollIcons" v-else-if="header=='Study budy'">
               <img src="/icons/star 42.svg" alt="study" />
              </div>
               <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
               <img src="/icons/star 42.svg" alt="study" />
              </div>
            </div>
            <div :class="customClasses['icon-8']">
               <div class="rollIcons" v-if="header =='Integrated learning'">
                <img src="/icons/union.svg" alt="study" />
              </div>
               <div class="rollIcons" v-else-if="header=='Study budy'">
                  <img src="/icons/union.svg" alt="study" />
              </div>
               <div class="rollIcons" v-show="header =='Screentime evolved' || header =='' ">
                  <img src="/icons/union.svg" alt="study" />
              </div>
            </div>
          
          </div>
        </div>
      </div>
    </div>
  </SfSection>
</template>
<script>
import {
  SfSection,
  SfImage,SfHeading,

  SfAccordion,
  SfList,
  
    SfMenuItem 
  
} from '@storefront-ui/vue';
import { ref } from '@vue/composition-api';
export default {
  name: 'Animations',
  components: {
    SfSection,
    SfImage,SfHeading,

    SfAccordion, SfList, SfMenuItem
  },
  setup(){
      const header = ref("");
      const showChevron = ref(false);
      const openHeader =ref("");
      let classes_default ={
        'icon-1':'icon-1',
        'icon-2':'icon-2',
        'icon-3':'icon-3',
        'icon-4':'icon-4',
        'icon-5':'icon-5',
        'icon-6':'icon-6',
        'icon-7':'icon-7',
        'icon-8':'icon-8'
        
      }
      const customClasses =ref(classes_default);
     
    return{
        header,
        showChevron,
        customClasses,
        openHeader

    }
  },
  mounted(){
       this.$watch(
        () => {
            return this.$refs.acc._data.openHeader
        },
      (val) => {
        this.header = val
        if(this.header =='Study budy'){
          this.customClasses['icon-1'] ='withcircleImg_icon1'
          this.customClasses['icon-2'] ='icon-2'
          this.customClasses['icon-3'] ='icon-3'
            this.customClasses['icon-4'] ='icon-4'
            this.customClasses['icon-5'] ='icon-5'
            this.customClasses['icon-6'] ='icon-6';
            this.customClasses['icon-7'] ='icon-7';
            this.customClasses['icon-8'] ='icon-8';
          }
          if(this.header =="Screentime evolved"){
            this.customClasses['icon-1'] ='icon-1';
            this.customClasses['icon-5'] ='withAnimImg_icon5';
            this.customClasses['icon-6'] ='withicon5_icon6';
            this.customClasses['icon-4'] ='withicon5_icon4';
            this.customClasses['icon-3'] ='withicon5_icon3';
          }
          if(this.header =='Integrated learning'){
             this.customClasses['icon-1'] ='icon-1';
            this.customClasses['icon-5'] ='withicon4_icon5';
            this.customClasses['icon-6'] ='withicon4_icon6';
            this.customClasses['icon-4'] ='withAnimImg_icon4';
          }
          this.header==""?this.customClasses =this.classes_default:""
        
      }
    )
  },
  methods: {
    changeHeader(headerName,fullText="") {
      console.log("hello")
     
      if(headerName !="Study" && this.header == headerName){
        this.header ="Study";
         
        return ;

      }
       this.header = headerName
       this.openHeader = fullText == this.openHeader?"":fullText;
    },
  },
};
</script>
<style lang="scss" >

.h2_miko3 {
  --heading-text-align: start;
    .h2{
    
    font-family: degular_black;
    color: #0B3533;
    letter-spacing: -2px;
    text-align: start;
      @include for-desktop {
    font-size: 54px;
    line-height: 74px;
     text-align: start;
    margin:0 3rem;
    }
    @include for-mobile {
      font-size: 2rem;
      line-height: 2rem;
       text-align: center;
    }
    }
  
}
.sf-accordion-item{
  .sf-accordion-item__header::after{
      position: absolute;
      content: "+";
      left: -28px;
      color: #55ABDB;
      font-size: 45px;
  }
  .sf-accordion-item__header.is-open::after{
      position: absolute;
      content: "-";
      left: -28px;
      color: #55ABDB;
      font-size: 45px;
  }
}
.title {
  --heading-title-font-weight: var(--font-weight--semibold);
  --section-margin: var(--spacer-xl) 0;
  --section-content-margin: var(--spacer-xl) 0;
  --heading-title-font-size: var(--h2-font-size);
  @include for-desktop {
    --section-margin: var(--spacer-2xl) 0;
    --section-content-margin: var(--spacer-2xl) 0;
  }
}
.bannerImg{
  display: none;
   @include for-mobile {
     display: block;
     .mobileImg{
      width: 100%;
     }
     
   }
}
 .animations_container_mob{
    position: relative;
     height: 15rem;
    .withcircleImg_icon1{
        top: 5%;
          position: absolute;
          left: 5%;
          transform: scale(1.2);
           animation: stretch-icon1 .5s alternate ease-in-out;
        img{
        height: 7.5rem;
        }
    }
    .withAnimImg_icon5{
            top: 35%;
       left: 30%;
        position: absolute;
       transform: scale(1.2);
         animation: stretch-icon1 .5s alternate ease-in-out;
         img{
          height: 6.5rem;
        }
    }
    .withicon4_icon5{
         top: 35%;
       left: 33%;
      position: absolute;
      animation: popDiv .5s alternate ease-in-out;
      img{
          height: 7.5rem; 
      }
    }
    .withicon5_icon6{
       top: 75%;
    left: 25%;
        transform: rotate(
    75deg);
    position: absolute;
       animation: roll90 .5s alternate ease-out 0s;
     position: absolute;
     img{
       height: 5rem;
     }

    }
    .withicon5_icon4{
           top: 40%;
    position: absolute;
    left: 80%;
        transform: scale(1.2);
          animation: stretch-icon1 .5s alternate ease-in-out;
          img{
        height: 3rem;
        }
    }
    .withicon5_icon3{
                top: 15%;
    left: 70%;
        position: absolute;
        transform: scale(1.2);
        animation: stretch-icon1 .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
    }
    .withAnimImg_icon4{
              top: 40%;
    position: absolute;
    left: 80%;
        transform: scale(1.5);
          animation: stretch-icon5 .5s alternate ease-in-out;
          img{
        height: 3rem;
        }
    }
    .withicon4_icon6{
        top: 75%;
    left: 25%;
       animation: popDiv .5s alternate ease-in-out;
      transform: rotate(
        0deg);
        position: absolute;
        img{
        height: 5rem;
        }
    }
      .icon-1{
          top: 5%;
          position: absolute;
          left: 5%;
           animation: popDiv .5s alternate ease-in-out;
        img{
        height: 5rem;
        }
     }
      .icon-2{
           top: 0%;
        left: 45%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
        
    }
      .icon-3{
          top: 10%;
    left: 70%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
//         transform: rotate(
// -20deg);
         img{
        height: 5rem;
        }
        
        
    }
      .icon-4{
          top: 40%;
    position: absolute;
    left: 80%;
        transform: rotate(180deg);
         animation: rollicons 0.5s alternate ease-out 0s;
          img{
        height: 3rem;
        }
    }
      .icon-5{
         top: 35%;
       left: 30%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
          height: 6.5rem;
        }
    }
    .icon-6{
      top: 75%;
    left: 25%;
       animation: popDiv .5s alternate ease-in-out;
        position: absolute;
         img{
       height: 5rem;
        }
    }
      .icon-7{
         top: 75%;
    position: absolute;
    left: 55%;
       animation: popDiv .5s alternate ease-in-out;
     img{
        height: 4rem;
        }
        
    }
     .icon-8{
       top: 40%;
        left: 5%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
        
  }
}
// .animations_container_mob{
//   position: relative;
//       height: 15rem;
//       .withcircleImg_icon1{
//         top: 5%;
//         animation: popDiv .5s alternate ease-in-out;
//         position: absolute;
//         left: 10%;
//           img{
//             height: 7rem;
//           }
//     }
//     .withAnimImg_icon5{
//       top: 30%;
//     left: 30%;
//     position: absolute;
//     animation: popDiv .5s alternate ease-in-out;
//     img{
//          height: 6rem; 
//     }
//     }
//     .withicon5_icon6{
//       left: 35%;
//       top: 60%;
//       transform: rotate(90deg);
//        animation: roll90 .5s alternate ease-out 0s;
//      position: absolute;
//      img{
//        height: 3rem;
//      }

//     }
//     .withicon5_icon4{
//       top: 28%;
//     position: absolute;
//     left: 65%;
//     img{
//       height: 3rem;
//     }
//     }
//     .withAnimImg_icon4{
//     top: 22%;
//     position: absolute;
//     left: 62%;
     
//       img{
//         height: 5.5rem;
//       }
//        animation: popDiv .5s alternate ease-in-out;
//     }
//     .withicon4_icon6{
//       left: 35%;
//       top: 60%;
//       transform: rotate(
//         0deg);
//     position: absolute;
//      img{
//      height: 4rem;
//     }
//     }
//     .icon-1{
//           top: 5%;
//           position: absolute;
//           left: 15%;
//         img{
//         height: 3rem;
//         }
//      }
//       .icon-2{
//            top: 0%;
//         left: 45%;
//         position: absolute;
//          img{
//         height: 3rem;
//         }
        
//     }
//       .icon-3{
//             top: 13%;
//           left: 65%;
//         position: absolute;
//          img{
//         height: 3rem;
//         }
        
        
//     }
//       .icon-4{
//           top: 40%;
//         position: absolute;
//         left: 70%;
//          animation: rollicons .5s alternate ease-out 0s;
//           img{
//         height: 3rem;
//         }
//     }
//       .icon-5{
//          top: 30%;
//          left: 35%;
//         position: absolute;
//          img{
//           height: 5.5rem;
//         }
//     }
//     .icon-6{
//        top: 70%;
//       left: 30%;

//         position: absolute;
//          img{
//        height: 4rem;
//         }
//     }
//       .icon-7{
//            top: 66%;
//     position: absolute;
//     left: 60%;
//      img{
//         height: 3rem;
//         }
        
//     }
//      .icon-8{
//        top: 35%;
//         left: 10%;
//         position: absolute;
//          img{
//         height: 4rem;
//         }
        
//       }
  
// }
 
  .animations_container{
    position: relative;
    width: 100%;
    height: 100%;
    .withcircleImg_icon1{
        top: 5%;
          position: absolute;
          left: 15%;
          transform: scale(1.2);
           animation: stretch-icon1 .5s alternate ease-in-out;
        img{
        height: 7.5rem;
        }
    }
    .withAnimImg_icon5{
        top: 20%;
         left: 40%;
        position: absolute;
        transform: scale(1.5);
         animation: stretch-icon5 .5s alternate ease-in-out;
         img{
          height: 6.5rem;
        }
    }
    .withicon4_icon5{
       top: 20%;
      left: 34%;
      position: absolute;
      animation: popDiv .5s alternate ease-in-out;
      img{
          height: 7.5rem; 
      }
    }
    .withicon5_icon6{
      top: 42%;
        transform: rotate(
    75deg);
    left: 35%;
    position: absolute;
       animation: roll90 .5s alternate ease-out 0s;
     position: absolute;
     img{
       height: 5rem;
     }

    }
    .withicon5_icon4{
       top: 27%;
        position: absolute;
        left: 80%;
        transform: scale(1.5);
          animation: stretch-icon5 .5s alternate ease-in-out;
          img{
        height: 3rem;
        }
    }
    .withicon5_icon3{
               top: 10%;
          left: 75%;
        position: absolute;
        transform: scale(1.2);
        animation: stretch-icon1 .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
    }
    .withAnimImg_icon4{
    top: 15%;
    position: absolute;
    left: 75%;
     
      img{
        height: 7.5rem;
      }
       animation: popDiv .5s alternate ease-in-out;
    }
    .withicon4_icon6{
      left: 40%;
      top: 40%;
       animation: popDiv .5s alternate ease-in-out;
      transform: rotate(
        0deg);
        position: absolute;
        img{
        height: 5rem;
        }
    }
      .icon-1{
          top: 5%;
          position: absolute;
          left: 15%;
           animation: popDiv .5s alternate ease-in-out;
        img{
        height: 5rem;
        }
     }
      .icon-2{
           top: 0%;
        left: 45%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
        
    }
      .icon-3{
            top: 10%;
          left: 75%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
//         transform: rotate(
// -20deg);
         img{
        height: 5rem;
        }
        
        
    }
      .icon-4{
          top: 27%;
        position: absolute;
        left: 80%;
        transform: rotate(180deg);
         animation: rollicons 0.5s alternate ease-out 0s;
          img{
        height: 3rem;
        }
    }
      .icon-5{
         top: 20%;
         left: 40%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
          height: 6.5rem;
        }
    }
    .icon-6{
       top: 40%;
      left: 30%;
       animation: popDiv .5s alternate ease-in-out;
        position: absolute;
         img{
       height: 6rem;
        }
    }
      .icon-7{
      top: 45%;
      position: absolute;
      left: 65%;
       animation: popDiv .5s alternate ease-in-out;
     img{
        height: 4rem;
        }
        
    }
     .icon-8{
       top: 25%;
        left: 15%;
        position: absolute;
         animation: popDiv .5s alternate ease-in-out;
         img{
        height: 5rem;
        }
        
  }
    }
    .rectangleShape{
          top: 42%;
        left: 47%;
        transform: rotate(
    -18deg);
      border-radius: 45%;
      width: 170px;
    /* background: yellow; */
    overflow: hidden;
      img{
        height: 90px;
        width: inherit;
         animation: popDiv .5s alternate ease-in-out;
      }
    }
  
    .rollIcons{
      transform: rotate(180deg);
       animation: rollicons .5s alternate ease-out 0s;
    }
    .rotate90{
       animation: popDiv .5s alternate ease-out 0s;
    }
    .smimg{
      height: 60px;
    }
  .animrotate{
    
    animation-iteration-count: 1;
      animation:   stretch
  3.5s, 
      roll 5.5s ;
  }
  .miko3_acrodianhead{
    margin-left: 25px;
  }
  #playImg-container{
    img{
        animation: popDiv .5s alternate ease-in-out;
        clip-path: polygon(50% 1%, 80% 10%, 100% 35%, 100% 70%, 80% 90%, 50% 100%, 20% 90%, 0% 70%, 0% 35%, 20% 10%);

    }
  }
  .hasImg{
    background-image: url("/icons/Rectangle 12.svg");
  }
  @keyframes popDiv { 
        0%   {transform: scale(0);}
        25%  {transform: scale(.2);}
        50%  {transform: scale(.5);}
        75%{
          transform: scale(.7);
        }
        100% {transform: scale(1);}
    }
     @keyframes rollicons {
      0% {
        transform: rotate(0);
      }
      25% {
        transform: rotate(45deg);
      }
       50% {
        transform: rotate(90deg);
      }
      75%{
        transform: rotate(135deg);
      }
      100% {
        transform: rotate(180deg);
      }
    }
      @keyframes roll90 {
      0% {
        transform: rotate(0);
      }
      25%  {transform:  rotate(25deg);}
      50% {
        transform: rotate(45deg);
      }
      75%{
        transform: rotate(75deg);
      }
      100% {
        transform: rotate(90deg);
      }
    }
    @keyframes stretch-icon1 {
      0% {
        transform: scale(.3);
        
      }
      50% {
        transform: scale(.7);
      }
      75% {
        transform: scale(1);
      }
      100% {
        transform: scale(1.2);
      }
  }
   @keyframes stretch-icon5 {
      0% {
        transform: scale(.3);
        
      }
      50% {
        transform: scale(.7);
      }
      75% {
        transform: scale(1.1);
      }
      100% {
        transform: scale(1.5);
      }
  }

.grid {
  display: flex;
  max-height: 20.625rem;
  width: 100%;
  justify-content: center;
  margin: 0;
  @include for-desktop {
    max-height: 40.625rem;
    max-width: 60rem;
    margin:0 3rem;
    // .bannerImg{
    //   display: none;
    // }
  }
     @include for-mobile {
        display: block;
        .animations_container{
          display: none;
        }
        // .bannerImg{
        //   display: block;
        // }
    }

    
  &__row {
    display: flex;
    flex-direction: column;
    & + & {
      margin-left: var(--spacer-xs);
      @include for-desktop {
        margin-left: var(--spacer-sm);
      }
        @include for-mobile {
        display: block;
      }
    }
  }
  &__col {
    width: 10rem;
    height: 10rem;
    @include for-desktop {
      &.small {
        height: 10rem;
      }
     width: 29.375rem;
     height: 29.375rem;
    }
      @include for-mobile {
       width: 100%;
    height: 100%;
    display: block;
        display: block;
    }
    & + & {
      margin-top: var(--spacer-xs);
      @include for-desktop {
        margin-top: var(--spacer-sm);
      }
    }
  }
}

</style>
