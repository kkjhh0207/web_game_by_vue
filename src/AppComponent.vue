<template>
  <WordChain2 />

  <WordChain2 />

  <WordChain2 />
</template>

<script>
import WordChain2 from "./components/Wordchain2.vue";
export default {
  name: "App",
  components: {
    WordChain2,
  },
  data() {
    return {
      word: "제로초",
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
