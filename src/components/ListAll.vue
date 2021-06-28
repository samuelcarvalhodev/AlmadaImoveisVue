<template>
  <div>
    <ul>
      <li>
        <label for="title"></label>
        <h2 id="title" name="title"></h2>
      </li>
      <li>
        <label for="description"></label>
        <h2 id="description" name="description"></h2>
      </li>
      <li>
        <label for="rooms"></label>
        <h2 id="rooms" name="rooms"></h2>
      </li>
      <li>
        <label for="vacancies"></label>
        <h2 id="vacancies" name="vacancies"></h2>
      </li>
      <li>
        <label for="area"></label>
        <h2 id="area" name="area"></h2>
      </li>
      <li>
        <label for="work-area"></label>
        <h2 id="work-area" name="work-area"></h2>
      </li>
      <li>
        <label for="location"></label>
        <h2 id="location" name="location"></h2>
      </li>
      <li>
        <label for="price"></label>
        <h2 id="price" name="price"></h2>
      </li>
      <li>
        <img src="path" alt="Casa" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    path: String,
  },
  methods: {},
};
</script>
