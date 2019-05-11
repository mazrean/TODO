<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter/>
    <ItemList/>
    <TODO/>
  </div>
</template>
<script>
import counter from "./Counter.vue";
import ItemList from "./ItemList.vue";
import TODO from "./TODO.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    counter,
    ItemList,
    TODO
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
