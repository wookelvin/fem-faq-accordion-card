<template>
  <button @click="onClick" class="faq-item" :class="{'show':show}">
    <div class="question">
      <strong>{{q}}</strong>
      <span class="icon" v-if="!show">+</span>
      <span class="icon" v-else>&#8211;</span>
    </div>
    <div class="answer">
      <slot></slot>
    </div>
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'FAQItem',
  emits: ['clicked'],
  props: {
    q: {
      type: String, 
      required: true
    }, 
    show: { 
      type: Boolean, 
      required: true
    }
  }, 
  methods:{ 
    onClick() { 
      this.$emit('clicked');
    }
  }
})
</script>

<style lang="scss" scoped>
@import "./../styles/_variables.scss";

.faq-item{
  padding-top:0.5em;
  padding-bottom:0.5em;
}
.question { 
  align-items:center;
  justify-content:space-between;
  display:flex;
  font-weight:300;
  font-size:1.25em;
  color: $color-neutral-text-blue2;
}

button:hover .question{
   color: $color-primary-red;
}
button { 
 border: none;
 background: transparent;
 padding: 0;
 width:100%;
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
   text-align:left;
   transition: 0.2s all ease;
   color: $color-neutral-text-blue2;
 }

 .faq-item.show{ 
   .question{ 
     font-weight:bold;
     color: inherit;
   }
   button{ 
     color: $color-neutral-text-blue1;
   }
   .answer{ 
     max-height:50px;
     padding-right:2em;
   }
 }
</style>
