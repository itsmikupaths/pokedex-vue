<template>
  <main>
    <div class="header">
      <p>{{ title }}</p>
    </div>
    <div class="pokemon-list">
      <article v-for="(pokemon, index) in pokemons" :key="'poke'+index">
        <img :src="imageUrl + pokemon.id + '.png'" width="96" height="96" :alt="pokemon.name">
        <h3>{{ pokemon.name }}</h3>
      </article>
    </div>
  </main>
</template>

<script>
export default {
  data () {
    return {
      title: "Pokemon",
      imageUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
      apiUrl: 'https://pokeapi.co/api/v2/pokemon',
      nextUrl: null,
      pokemons: [],
    }
  },
  created () {
    this.fetchData();
  },
  methods: {
    fetchData () {
      fetch(this.apiUrl)
      .then(res => res.json())
      .then(data => {
        this.nextUrl = data.next;
        data.results.forEach(pokemon => {
          pokemon.id = pokemon.url.split('/').filter(part => !!part).pop();
          this.pokemons.push(pokemon);
        });
      })
    },
  }
}
</script>

<style scoped>
.header {
  margin-bottom: 30px;
}
.header p {
  color: var(--text-accent);
  font-size: 42px;
  font-weight: 700;
  line-height: 42px;
  margin: 0 0;
}
.pokemon-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  grid-gap: 10px;
  width: 100%;
  max-width: 510px;
}
.pokemon-list article {
  height: 150px;
  text-align: center;
  text-transform: capitalize;
  border-radius: 5px;
  cursor: pointer;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2),
              0 15px 10px rgba(0, 0, 0, 0.2);
}
.pokemon-list article h3 {
  margin: 0;
}
</style>