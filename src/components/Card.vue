<template>
  <div class="wrapper">
    <div class="card">
      
      <div class="img-collection">
        <img src="/img/bg-pattern-desktop.svg" class="bg-img">
        <img src="/img/illustration-woman-online-desktop.svg">
      </div>
      
      <div class="card-body">
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
  width: $width-desktop;
  max-width: $width-desktop;
  padding: 4em;
  padding-left:40%;
  margin:8em;
  border-radius:1.5em;
  min-height:600px;
  box-shadow: 0 2em 2em -1em rgba(0, 0, 0, 0.25);
  overflow:hidden;
  position:relative;
}
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
.row{ 
  display: flex;
  justify-content: space-between;
}
.wrapper{ 
  position:relative;  
}
.box-img{
  position: absolute;
  left:-2.5%;
  top: 42.5%;
  width:20em;
  height:auto;
}
</style>
