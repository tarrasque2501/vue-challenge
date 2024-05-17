<template>
  <div>
    <ul>
      <li v-for="item in SearchData" :key="item.id">
        {{ item.id }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["SearchData"],
  data() {
    return {};
  },
  onMounted() {
    console.log("test");
    console.log(this.SearchData);
  },
};
</script>
