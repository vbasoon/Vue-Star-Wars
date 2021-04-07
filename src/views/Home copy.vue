<template>
  <div class="home"></div>
</template>

<script>
export default {
  name: "Home",
  data: (()=>{
    starWarsFilms:[]
  }),
  methods: {
    getStarWarsFilms = () => {
      fetch(`https://swapi.dev/api/films/`)
        .then((res) => res.json())
        .then((data) => {
          setFilms(data.results);
        });
    },
    getStarWarsPeople = () => {
      fetch(`https://swapi.dev/api/people/`)
        .then((res) => res.json())
        .then((data) => {
          setPeople(data.results);
        });
    },
    getStarWarsPlanets = () => {
      fetch(`https://swapi.dev/api/planets/`)
        .then((res) => res.json())
        .then((data) => {
          setPlanets(data.results);
        });
    }
  },
  components: {
  },
};
</script>
