<template>
    <label class="container" :style="{background:color}">
        <input type="radio" :name="name" :value="value" :checked="isSelected" :style="{background:color}" @change="onColorchange()">
        <span class="checkmark" :style="{background:color}"></span>
    </label>
</template>
<script>
export default {
    setup() {
        
    },
    methods:{
        onColorchange(){
            this.$emit('onColorChanged',this.colorname)
        }
    },
    props:['name','value','color','colorname','isSelected']
}
</script>
<style lang="scss" scoped>
/* The container */
.container {
  display: block;
  position: relative;
  padding-left: 35px;
  margin-bottom: 12px;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/* Hide the browser's default radio button */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

/* Create a custom radio button */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  border-radius: 50%;
}

/* On mouse-over, add a grey background color */


/* When the radio button is checked, add a blue background */
.container input:checked ~ .checkmark {
    width: 30px;
    height: 30px;
}

/* Create the indicator (the dot/circle - hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the indicator (dot/circle) when checked */
.container input:checked ~ .checkmark:after {
  display: block;
}

/* Style the indicator (dot/circle) */
.container .checkmark:after {
 	top: 4px;
	left: 4px;
	width: 60%;
	height: 60%;
	border-radius: 50%;
    border:2px solid white;

}
</style>