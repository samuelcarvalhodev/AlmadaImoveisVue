<template>
  <div >
    <header v-bind:style="{ margin: 0, padding: 0, border: '1px solid #f9f9', verticalAlign: 'baseline', backgroundColor: '#000', color: '#f7f7f7' }">
      <div  >
        <h1 class="h1 display-1">Almada Imóveis</h1>
      </div>
    </header>
    <hr />
    <main>
      <div id="form" class="mb-3">
        <form id="formulario" class="insert-form" @submit.prevent="insertData">
          <h4 class="h4 display-4">Inserir anúncio</h4>
          <br>
          <label class="form-label" for="title">Título:</label>
          <input class="form-control" type="text" id="title" name="title" v-model="title" required />
          <label class="form-label" for="description">Descrição:</label>
          <input class="form-control"
            type="text"
            id="description"
            name="description"
            v-model="description"
            required
          />
          <label class="form-label" for="rooms">Quartos:</label>
          <input class="form-control" type="text" id="rooms" name="rooms" v-model="rooms" required />
          <label class="form-label" for="vacancies">Vagas de garagem:</label>
          <input class="form-control"
            type="text"
            id="vacancies"
            name="vacancies"
            v-model="vacancies"
            required
          />
          <label class="form-label" for="area">Área de terreno:</label>
          <input class="form-control" type="text" id="area" name="area" v-model="area" required />
          <label class="form-label" for="work-area">Área construída:</label>
          <input class="form-control"
            type="text"
            id="work-area"
            name="work-area"
            v-model="workArea"
            required
          />
          <label class="form-label" for="location">Localidade:</label>
          <input class="form-control"
            type="text"
            id="location"
            name="location"
            v-model="location"
            required
          />
          <label class="form-label" for="price">Preço:</label>
          <input class="form-control" type="text" id="price" name="price" v-model="price" required />
          <label class="form-label" for="image">Imagem:</label>
          <input class="form-control" type="text" id="image" name="image" v-model="image" required />

          <div class="d-grid gap-2 col-6 mx-auto">
            <button id="insert" type="submit" class="btn btn-success" >Inserir</button>
            <button id="insert" v-on:click="ListAll()" class="btn btn-primary mb-3">Listar</button>
            <input class="btn btn-danger" type="reset" value="Reset">
          </div>
        </form>
      </div>
    </main>
    <main id="list" v-if="test">
      <div>
        <label class="form-label">Titulo</label>
        <p>{{ this.title }}</p>
        <br>
        <label class="form-label" for="">Descrição</label>
        <p>{{ this.description }}</p>
        <br>
        <label class="form-label" for="">Quartos</label>
        <p>{{ this.rooms }}</p>
        <br>
        <label class="form-label" for="">Vagas de garagem</label>
        <p>{{ this.vacancies }}</p>
        <br>
        <label class="form-label" for="">Área de terreno</label>
        <p>{{ this.area }}</p>
        <br>
        <label class="form-label" for="">Área construída</label>
        <p>{{ this.workArea }}</p>
        <br>
        <label class="form-label" for="">Localidade</label>
        <p>{{ this.location }}</p>
        <br>
        <label class="form-label" for="">Preço</label>
        <p>{{ this.price }}</p>
        <br>
        <label class="form-label" for="">Foto da casa</label>
        <span>
          <img v-bind="image" alt="imagem da casa" >
        </span>
      </div>
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
    }
    

  },

  methods: {
    ListAll() {
      this.test = true;
    },

    insertData: function(){
      var announce = {
        title: this.title,
        description: this.description,
        rooms: this.rooms,
        vacancies: this.vacancies,
        area: this.area,
        workArea: this.workArea,
        location: this.location,
        price: this.price,
        image: this.image
      }

      console.log(announce);
      localStorage.setItem("announces", JSON.stringify(announce));
      // this.title = localStorage.setItem("teste", this.title)
      
    },
  }
}
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

.insert-form input  {
  margin-bottom: 1%;
  height: 25px;
  /* border-radius: 8px; */
  border: 1px solid #777;
  transition: border 02s;
  padding-left: 5px;
}

.insert-form input [type="text"]:focus {
  outline: none;
  border: none;
  border-bottom: 1px solid #e40f0f;
}
</style>
