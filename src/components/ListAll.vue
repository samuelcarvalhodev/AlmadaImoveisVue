<template>
  <div>
    <ul class="list-unstyled">
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="title">Titulo</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="title" name="title">{{this.title}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="description">Descrição</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="description" name="description">{{this.description}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="rooms">Quartos</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="rooms" name="rooms">{{this.rooms}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="vacancies">Vagas de garagem</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="vacancies" name="vacancies">{{this.vacancies}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="area">Área total</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="area" name="area">{{this.area}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="work-area">Área construída</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="work-area" name="work-area">{{this.workArea}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="location">Localidade</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="location" name="location">{{this.location}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="price">Preço</h2>
        <p class="fst-italic text-nowrap bd-highlight" id="price" name="price">{{this.price}}</p>
      </li>
      <li class="text-center">
        <h2 class="h2 display-6 text-decoration-underline" for="image">Foto da casa</h2>
        <div class="card mb-3" style="width: 18rem; marginRight: auto; marginLeft: auto">
          <img id="image" :src="path" alt="Casa" class="card-img-top" />
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    path: String,
  },
  data() {
    return{
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

  beforeMount(){
    this.getAnnounces()
  },
  methods: {
    getAnnounces(){
      var announce = localStorage.getItem("announces");
      var announceObj = JSON.parse(announce);
      console.log(announceObj);

      this.title = announceObj.title;
      this.description = announceObj.description;
      this.rooms = announceObj.rooms;
      this.vacancies = announceObj.vacancies;
      this.area = announceObj.area;
      this.workArea = announceObj.workArea;
      this.location = announceObj.location;
      this.price = announceObj.price;
      this.path = announceObj.image;

    }
  },
};
</script>
