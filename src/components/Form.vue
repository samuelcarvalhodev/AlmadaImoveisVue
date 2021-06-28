<template>
  <div>
    <header>
      <div class="page-title">
        <h1>Almada Imóveis</h1>
      </div>
    </header>
    <hr />
    <main>
      <div id="form">
        <form id="formulario" class="insert-form" @submit.prevent="ListAll">
          <h4>Inserir anúncio</h4>
          <label for="title">Título:</label>
          <input type="text" id="title" name="title" v-model="title" required />
          <label for="description">Descrição:</label>
          <input
            type="text"
            id="description"
            name="description"
            v-model="description"
            required
          />
          <label for="rooms">Quartos:</label>
          <input type="text" id="rooms" name="rooms" v-model="rooms" required />
          <label for="vacancies">Vagas de garagem:</label>
          <input
            type="text"
            id="vacancies"
            name="vacancies"
            v-model="vacancies"
            required
          />
          <label for="area">Área de terreno:</label>
          <input type="text" id="area" name="area" v-model="area" required />
          <label for="work-area">Área construída:</label>
          <input
            type="text"
            id="work-area"
            name="work-area"
            v-model="workArea"
            required
          />
          <label for="location">Localidade:</label>
          <input
            type="text"
            id="location"
            name="location"
            v-model="location"
            required
          />
          <label for="price">Preço:</label>
          <input type="text" id="price" name="price" v-model="price" required />
          <label for="image">Imagem:</label>
          <input type="text" id="image" name="image" v-model="image" required />

          <div class="btn-container">
            <button id="clear">Limpar</button>
            <button id="insert" type="submit">Inserir</button>
            <button id="insert" v-on:click="ListAll()">Listar</button>
          </div>
        </form>
      </div>
    </main>
    <main id="list" v-if="test">
      <p>apareceu</p>
    </main>
  </div>
</template>

<script>
export default {
  props: {
    test: Boolean,
  },
  data() {
    return {
      title: "",
      rooms: "",
      description: "",
      vacancies: "",
      area: "",
      workArea: "",
      location: "",
      price: "",
      image: "",
    };
  },

  methods: {
    ListAll() {
      this.test = true;
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.page-title {
  border: 1px solid #000;
  background-color: #000;
  color: #ffff;
  text-align: center;
  height: 70px;
}

.page-title h1 {
  padding: 1%;
}

#form h4 {
  font-size: 23px;
  text-align: center;
}

.insert-form {
  display: flex;
  flex-direction: column;
  margin-left: 10%;
  margin-right: 10%;
}

.insert-form input {
  margin-bottom: 1%;
  height: 25px;
  /* border-radius: 8px; */
  border: 1px solid #777;
  transition: border 02s;
  padding-left: 5px;
}

.insert-form input[type="text"]:focus {
  outline: none;
  border: none;
  border-bottom: 1px solid #e40f0f;
}
</style>
