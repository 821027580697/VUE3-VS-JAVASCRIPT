<template>
  <div>
    <div :style="styleObject">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium,
      adipisci impedit. Ad cum deserunt dolor error excepturi laboriosam, magnam
      maiores minus perferendis porro provident quaerat sed temporibus veniam
      voluptate voluptatibus!
    </div>
    <button v-on:click="fontSize--">-</button>
    <button v-on:click="fontSize++">+</button>
  </div>
</template>

<script>
import {computed, ref} from "vue";

export default {
  setup() {
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: '13px'
    // });
    const fontSize = ref(13);
    const styleObject = computed(() => {
      return {
        color: "red",
        fontsize: fontSize.value + 'px'
      };
    });
    return {
      styleObject,
      fontSize,
    };
  },
};
</script>

<style scoped></style>