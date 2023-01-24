<template>
  <div>{{ first }} 곱하기 {{ second }} 는?</div>
  <form v-on:submit="onSubmitForm">
    <!--인풋과 데이터 value를 연결-->
    <input type="number" v-model="value" />
    <!--submit은 form을 제출-->
    <button type="submit">입력</button>
    <div id="result">{{ result }}</div>
  </form>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      first: Math.ceil(Math.random() * 9),
      second: Math.ceil(Math.random() * 9),
      value: "",
      result: "",
    };
  },
  methods: {
    onSubmitForm(e) {
      e.preventDefault(); //페이지 새로고침 방지
      console.log(this.first);
      console.log(this.second);
      if (this.first * this.second == this.value) {
        this.result = "정답";
      } else {
        this.result = "땡";
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
