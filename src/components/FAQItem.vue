<template>
  <div class="faq-item" :class="{'show':show}">
    <button class="question" @click="show = !show">
      <strong>{{q}}</strong>
      <span class="icon" v-if="!show">+</span>
      <span class="icon" v-else>&#8211;</span>
    </button>
    <div class="answer">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
export default defineComponent({
  name: 'FAQItem',
  props: {
    q: {
      type: String, 
      required: true
    }
  }, 
  data: () => ({ 
    show: false,
  })
})
</script>

<style lang="scss" scoped>
@import "./../styles/_variables.scss";

.faq-item{
  padding-top:0.5em;
  padding-bottom:0.5em;
}

button { 
  align-items:center;
  justify-content:space-between;
  display:flex;
 border: none;
 background: transparent;
 font-weight:bold;
 padding: 0;
 width:100%;
 font-size:1.25em;
 color: $color-neutral-text-blue2;
 .icon{ 
  color: $color-primary-red;
  font-size:2em;
  width:1em;
  display:inline-block;
  text-align:center;
 }
 
 cursor: pointer;
 &:hover{ 
   .icon{
     color: darken($color-primary-red, 5%);
   }
 }
 &:focus{ 
   outline:none;
   border:none;
 }
}

 .answer{ 
   transform-origin: top center;
   max-height: 0px;
   overflow:hidden;
   transition: 0.2s all ease;
 }

 .faq-item.show{ 
   button{ 
     color: $color-neutral-text-blue1;
   }
   .answer{ 
     max-height:50px;
   }
 }
</style>
