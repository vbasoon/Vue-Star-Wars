<template>
  <div class="home">
    <h1>This is a Home page</h1>
    <h2>Films:</h2>
    <ul>
      <li v-for="film in films" :key="film.title" class="col">
        <div class="card">
          <div class="card__content">
            <div class="card__header">
              <h2>{{ film.title }}</h2>
              <h3>{{ film.director }}</h3>
              <strong>
                <p>{{ film.release_date }}</p>
              </strong>
            </div>
            <div class="card__desc">
              <strong>Description</strong>
              <p>{{ film.opening_crawl }}</p>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      films: [],
    };
  },
  mounted() {
    fetch(`https://swapi.dev/api/films/`)
      .then((res) => res.json())
      .then((data) => (this.films = data.results))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style scoped>
li {
  list-style-type: none;
}
</style>
