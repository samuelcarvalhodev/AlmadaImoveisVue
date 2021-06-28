<template>
  <div id="app">
    <Form v-if="!renderList" />
    <ListAll v-if="renderList" />
    <button
      v-if="!renderList"
      v-on:click="handleList('list')"
      class="btn btn-info"
    >
      Listar Todos
    </button>
    <button
      v-if="renderList"
      v-on:click="handleList('return')"
      class="btn btn-info"
    >
      Voltar
    </button>
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import ListAll from "./components/ListAll.vue";

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
    handleList(e) {
      if (e === "list") {
        this.renderList = true;
      } else if (e === "return") {
        this.renderList = false;
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
