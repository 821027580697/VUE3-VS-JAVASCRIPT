<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h3>강의가 있습니까?</h3>
    <!--    <p>{{ teacher.lectures.length > 0 ? "있습니다 " : "없습니다." }}</p>-->
    <p>{{ hasLectures }}</p>
    <p>{{ hasLectures }}</p>
    <p>{{ existLectures() }}</p>
    <p>{{ existLectures() }}</p>
    <button v-on:click="counter++">Counter: {{ counter }}</button>
    <h2>이름</h2>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";

export default {
  setup() {
    const teacher = reactive({
      name: "짐코딩",
      lectures: ["HTML/CSS", "Javascript", "Vue3"],
    });

    const hasLectures = computed(() => {
      return teacher.lectures.length > 0 ? "있음" : "없음";
    });

    const existLectures = () => {
      return teacher.lectures.length > 0 ? "있음" : "없음";
    };

    const counter = ref(0);

    const firstName = ref("홍");
    const lastName = ref("길동");

    const fullName = computed({
      get() {
        return firstName.value + " " + lastName.value;
      },
      set(value) {
        [firstName.value, lastName.value] = value.split(' ')
      },
    });
    console.log('console 출력 : ', fullName.value)
    fullName.value ='짐 코딩'
    return {
      teacher,
      hasLectures,
      existLectures,
      counter,
      fullName,
    };
  },
};
</script>

<style scoped></style>
<!--같은 코드를 작성했을 때 -->
<!--computed를 사용했을 때와 -->
<!--method를 사용했을 때 console을 찍어보니  -->
<!--method는 2번 호출함.-->
<!--성능적으로 computed가 더 좋음. -->
<!--computed는 cache로 보내 가지고 있다가 호출되면 보여주기 때문 -->
<!--cache의 변경 시점은 데이터가 변경될 때-->