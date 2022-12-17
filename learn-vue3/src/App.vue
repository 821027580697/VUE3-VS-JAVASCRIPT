

<template>
  <div>
    <p>{{ msg }}</p>
    <p v-text="msg"></p>
    <p v-html="htmlStr"></p>
    <p v-text="htmlStr"></p>
    <p v-pre>{{ msg }}</p>
    <p>{{ htmlStr}}</p>
    <p v-once>{{msg}}!!!!!</p>
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  setup() {
    const msg = ref('안녕하세요')
    const htmlStr = ref('<strong>안녕</strong>')
    return {
      msg,
      htmlStr
    }
  }
}
</script>

<style scoped>

</style>
<!--#디렉티브-->
<!--v-text-->
<!--v-html-->
<!--v-show-->
<!--v-if-->
<!--v-else-->
<!--v-else-if-->
<!--v-for-->
<!--v-on-->
<!--v-bind-->
<!--v-model-->
<!--v-slot-->
<!--v-pre-->
<!--v-once-->
<!--v-cloak-->
<!--v-memo-->