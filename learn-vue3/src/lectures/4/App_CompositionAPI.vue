<template>
  <div>
    <h2>반응형 메세지</h2>
    <p>{{ reactiveMessage }}</p>
    <button v-on:click="addReactiveMessage">Add Message</button>
    <h2>일반 메세지</h2>
    <p>{{ nomalMessage }}</p>
    <button v-on:click="addNomalMessage">Add Message</button>
  </div>
</template>

<script>
import {isRef, onBeforeMount, onMounted, ref} from "vue";

export default {
  setup() {
    console.log("setup");
    const reactiveMessage = ref("Hello Reactive Message");
    const addReactiveMessage = () => {
      reactiveMessage.value = reactiveMessage.value + "!";
    };

    console.log("isRef(reactiveMessage) : ", isRef(reactiveMessage));
    let nomalMessage = "Hello Normal Message";
    const addNomalMessage = () => {
      nomalMessage = nomalMessage + "!";
    };
    console.log("isRef(nomalMessage) : ", isRef(nomalMessage));

    onMounted(() => {
      console.log("onMounted");
    });

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });
    return {
      reactiveMessage,
      nomalMessage,
      addReactiveMessage,
      addNomalMessage,
    };
  },
};
</script>

<style scoped></style>