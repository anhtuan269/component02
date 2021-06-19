<template>
  <div class="container">
    <Item
      v-for="(item, index) in items"
      :key="index"
      :item="item"
      :vertical="item.vertical"
    >
    </Item>
  </div>
</template>

<script>
import Item from "@/components/Item";

export default {
  name: "App",
  components: {
    Item,
  },
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/items")
      .then((res) => res.json())
      .then((data) => (this.items = data))
      .catch((err) => console.log(err));
  },
  computed: {},
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

