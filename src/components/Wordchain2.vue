<template>
  <div>
    <div>{{ word }}</div>
    <form v-on:submit="onSubmitForm">
      <input type="text" v-model="value" ref="answer" />
      <button>입력</button>
      <div>{{ result }}</div>
    </form>
  </div>
</template>

<script>
export default {
  name: "WordChain2",
  components: {},
  props: ["startWord"],
  data() {
    return {
      word: this.startWord,
      reulst: "",
      value: "",
    };
  },
  methods: {
    onSubmitForm(e) {
      e.preventDefault();
      if (this.word[this.word.length - 1] === this.value[0]) {
        this.result = "정답";
        this.word = this.value;
        this.value = "";
        this.$refs.answer.focus();
      } else {
        this.result = "땡";
        this.value = "";
        this.$refs.answer.focus();
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
