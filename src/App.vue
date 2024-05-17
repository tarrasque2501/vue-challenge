<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <giphy-search @emitedData="recieveEmitedData"></giphy-search>
  <giphy-result
    v-if="this.mainResult != null"
    SearchData="this.mainResult.data"
  ></giphy-result>

  <button type="button" @click="test">test</button>
</template>

<script>
import GiphySearch from "./components/Giphy-Search.vue";
import GiphyResult from "./components/Giphy-Result.vue";

export default {
  name: "App",
  components: {
    GiphySearch,
    GiphyResult,
  },
  data() {
    return {
      mainResult: null,
    };
  },
  methods: {
    recieveEmitedData(data) {
      this.mainResult = data;
    },
    test() {
      console.log("test");
      console.log(this.mainResult.data[1]);
    },
  },
  onMount() {
    console.log(this.mainResult);
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
