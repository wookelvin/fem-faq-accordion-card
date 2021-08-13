<template>
  <div class="card row">
    <div class="col-6">
      <div class="img-collection">
        <img src="/img/illustration-woman-online-desktop.svg">
        <img src="/img/bg-pattern-desktop.svg">
      </div>
    </div>
    <div class="col-6">
      <slot></slot>   
    </div>
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
  background:white;
  max-width: 100%;
  width: $width-desktop;
  padding: 4em;
  border-radius:1.5em;
  box-shadow: 0 2em 2em -1em rgba(0, 0, 0, 0.25);
}
.img-collection { 
  position: relative;
  margin-left:-10em;
}
img{ 
  position:absolute;
  top:0;
  left:0;
  right:0;
  bottom:0;
  display:block;
  object-fit: contain;
}
.row{ 
  display: flex;
}
.col-6{ 
  width:50%;
}
</style>
