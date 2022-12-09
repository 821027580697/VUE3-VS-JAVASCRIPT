<template>
  <div>
    <h2>보간법</h2>
    <p>문자열 : {{ message }}</p>
    <p v-once> {{ message }}</p>
    <button v-on:click="message = message + '!'">click!</button>
    <hr/>
    <h2>v-html</h2>
    <p>{{ rawHtml }}</p>
    <p v-html="rawHtml"></p>
    <hr>
    <div :title="dynamicTitle">마우스를 올려보세요</div>
    <input type="text" value="송수용" :disabled="isInputDisabled">
    <input v-bind="attrs">
    <h2>javascript</h2>
    {{ message.split('').reverse().join('')}}<br />
    {{ isInputDisabled ? '예' : '아니오'}}

  </div>
</template>

<script>
import {ref} from "vue";

export default {
  setup() {
    const message = ref('안녕하세요!');
    const rawHtml = ref('<strong>안녕하세요</strong>')

    const dynamicTitle = ref('안녕!')
    const isInputDisabled = ref(true)
    const attrs = ref({
      type:'password',
      value:'12345678',
      disabled:false
    })
    return {
      message,
      rawHtml,
      isInputDisabled,
      dynamicTitle,
      attrs
    }
  }

}
</script>

<style scoped>

</style>