<template>
  <div v-if="liked">좋아요 눌렀음</div>
  <button v-else v-on:click="onClickButton">like</button>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      liked: false,
    };
  },
  methods: {
    onClickButton() {
      this.liked = true;
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
