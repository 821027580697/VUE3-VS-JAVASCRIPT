<template>
  <div>
    <ul>
      <template v-for="(item, index) in evenItems" :key="item.id">
        <!--        <li v-if="item.id % 2 === 0">-->
        <li v-if="item.id % 2 === 0">
          ID: {{ item.id }},
          인덱스: {{ index }},
          {{ item.message}}
        </li>
      </template>
    </ul>
    <hr/>
    <ul>
      <li v-for="(value, key, index) in myObject" :key="key">
        {{ index }} - {{ key }} - {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import {computed, reactive} from "vue";

export default {
  setup() {
    const items = reactive([
      { id: 1, message: "Java" },
      { id: 2, message: "HTML" },
      { id: 3, message: "CSS" },
      { id: 4, message: "Javascript" },
    ]);

    const evenItems = computed(() => items.filter(item => item.id % 2 === 0))

    const myObject =reactive({
      title:'제목',
      author:'홍길동',
      published:'2015-12-13'
    })
    return {
      items,
      evenItems,
      myObject
    };
  },
};
</script>

<style scoped></style>
<!--#for 랜더링-->
<!-- v-for와 v-if를 동시에 사용하는 것은 좋지 않다.-->
<!--그래서 template를 사용하여 한번 덮어주고, 그 안에 있는-->
<!--태그에 v-if를 활용한다.-->
<!--<li v-for="( value, key, index) in myObject" :key="key">-->
<!--{{ key }} - {{ value }} - {{ index }}-->
<!--</li>-->