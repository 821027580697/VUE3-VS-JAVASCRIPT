<template>
  <div>
    <div class="text" :class="[isActive ? 'active-class' : 'class', errorClass, classObject]">텍스트!</div>
    <button v-on:click="toggle">toggle</button>
    <button v-on:click="hasError = !hasError">toggleError</button>
  </div>
</template>

<script>
import {computed, ref} from "vue";

export default {
  setup() {
    const isActive = ref(true);
    const hasError = ref(false);

    // const classObject = reactive({
    //   active: true,
    //   'text-danger':true,
    // })

    const classObject = computed(() => {
      return {
        active: true && true,
        'text-danger': true && true,
        'text-blue':true
      };
    });

    const activeClass = ref('active')
    const errorClass = ref('error')
    const toggle = () => {
      isActive.value = !isActive.value
    }

    return {
      isActive,
      toggle,
      hasError,
      classObject,
      activeClass,
      errorClass
    }

  }
}
</script>

<style scoped>
.active {
  font-weight:  900;
}
.text-danger {
  color: red;
}
</style>
클래스 스타일 바인딩 하는 법
객체 바인딩
# 디렉티브 제한 사항 공식문서 참고
#