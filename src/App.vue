<template>
  <div id="app">
    <Form v-if="!renderList" />
    <!-- <ListTable /> -->
    <ListAll v-if="renderList" />
    <button v-on:click="handleList" class="btn btn-info">Listar Todos</button>
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import ListAll from "./components/ListAll.vue";
// import ListTable from "./components/ListTable.vue";

export default {
  name: "App",
  components: {
    Form,
    ListAll,
    // ListTable,
  },
  props: {
    renderList: Boolean,
  },

  methods: {
    handleList() {
      this.renderList = true;
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
