<template>
  <div>끝말잇기 : {{ target }}</div>
  <form v-on:submit="onSubmitForm">
    <!--인풋과 데이터 value를 연결-->
    <input type="text" ref="answer" v-model="value" />
    <!--submit은 form을 제출-->
    <button type="submit">입력</button>
    <div v-if="!target" id="result">시작 단어를 입력하세요</div>
    <div v-else id="result">{{ result }}</div>
  </form>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      target: "",
      value: "",
      result: "",
    };
  },
  methods: {
    onSubmitForm(e) {
      e.preventDefault(); //페이지 새로고침 방지
      console.log(this.target);
      console.log(this.value);
      if (this.target == "") {
        this.target = this.value;
        this.value = "";
        this.$refs.answer.focus();
      } else {
        console.log("target" + this.target[this.target.length - 1]);
        if (this.target[this.target.length - 1] == this.value[0]) {
          this.target = this.value;
          this.result = "정답";
          this.value = "";
          this.$refs.answer.focus();
        } else {
          this.result = "오답";
          this.value = "";
          this.$refs.answer.focus();
        }
      }
      console.log("1" + this.target);
      console.log("1" + this.value);
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
