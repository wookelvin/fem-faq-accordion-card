<template>
  <div class="wrapper">
    <div class="card">
      
      <div class="img-collection">
        <img src="/img/bg-pattern-desktop.svg" class="bg-img">
        <img src="/img/illustration-woman-online-desktop.svg">
      </div>
      
      <div class="card-body">
        <div class="img-mobile">
          <img src="/img/bg-pattern-mobile.svg" class="bg-img">
          <img src="/img/illustration-woman-online-mobile.svg" >
        </div>
        <slot></slot>   
      </div>
    </div>
    <img src="/img/illustration-box-desktop.svg" class="box-img">
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
export default defineComponent({
  name: 'Card',
})
</script>

<style lang="scss" scoped>
@import "./../styles/_variables.scss";

.card{ 
  box-sizing: border-box;
  background:white;
  padding: 4em;
  padding-left:45%;
  border-radius:1.5em;
  min-height:600px;
  box-shadow: 0 2em 2em -1em rgba(0, 0, 0, 0.25);
  overflow:hidden;
  position:relative;
}
.img-collection{
  img{ 
    position:absolute;
    top: 7.5%;
    left: -10%;
    width: 50%;
    height:auto;
    display: block;
  }
  img.bg-img{ 
    transform-origin: right center;
    transform: scale(200%);
    top: -10%;
  }
}
.row{ 
  display: flex;
  justify-content: space-between;
}
.wrapper{ 
  box-sizing: border-box;
  position:relative;  
  width: $width-desktop;
  max-width: $width-desktop;
  padding-left: 8em;
  padding-right: 8em;
  padding-top:5em;
  padding-bottom:5em;
}
.box-img{
  position: absolute;
  left:-2.5%;
  top: 42.5%;
  width:20em;
  height:auto;
}
.img-mobile{ 
  display:none;
}

@media screen and (max-width: 1440px) {
  .box-img,.img-collection{
    display:none;
  }
  .wrapper { 
    width: $width-mobile;
    max-width:$width-mobile;
    padding-left:0;
    padding-right:0;
  }
  .card{ 
    padding-top:10em;
    padding-left:2em;
    padding-right:2em;
    padding-bottom:2em;
    min-height:675px;
    overflow:inherit;
  }

  .img-mobile{    
    display:block; 
    img{ 
      position:absolute;
      width: $width-mobile - 35px;
      height:auto;
      top:-8.5em;
      margin-left: -2em;
      margin-right: -2em;
      display:block;
    }
    img.bg-img{ 
      top:0;
      left:0;
      right:0;
      width: $width-mobile - 50px;
      position:absolute;
      margin-left:auto;
      margin-right:auto;
    }
  }
}
</style>
