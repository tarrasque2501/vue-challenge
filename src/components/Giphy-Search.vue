<template>
  <h1>Search on Giphy</h1>
  <input type="text" v-model="searchValue" />
  <button type="button" @click="connectToGiphy(searchValue)">Search</button>
  <giphy-result></giphy-result>
</template>

<script>
export default {
  props: ["SearchData"],
  data() {
    return {
      searchResult: null,
      searchValue: "",
    };
  },
  methods: {
    connectToGiphy(value) {
      fetch(
        "https://api.giphy.com/v1/gifs/search?" +
          new URLSearchParams({
            api_key: "pLURtkhVrUXr3KG25Gy5IvzziV5OrZGa",
            q: value,
            limit: 20,
          })
      ).then((response) => {
        response.json().then((data) => {
          this.searchResult = data;
          this.$emit("emitedData", this.searchResult);
        });
      });
    },
  },
};
</script>
