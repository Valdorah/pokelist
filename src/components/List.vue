<template>
  <div>
    <button v-on:click="fakeAdd">Fake Add</button>
    <table class="translucide">
      <tr>
        <th>Picture</th>
        <th>Name</th>
      </tr>
      <myLine
        v-for="(pokemon, index) in pokemons"
        :tab="pokemons"
        :id="index"
        :key="index"
        :name="pokemon.name"
        :image="pokemon.image"
      />
    </table>
  </div>
</template>

<script>
import myLine from "./Line.vue";

export default {
  name: "List",
  components: {
    myLine
  },
  data: () => {
    return {
      pokemons: []
    };
  },
  methods: {
    fakeAdd: function() {
      this.pokemons.push({
        name: "toto",
        image: "http://ekladata.com/fjamASyyrGCJULj0HEjYmhJRLvE.gif"
      });
    },
    getFewPokemons: function() {
      let tmp = this
      for (let i = 1; i <= 20; i++) {
        var data = null;

        var xhr = new XMLHttpRequest();

        xhr.addEventListener("readystatechange", function() {
          if (this.readyState === this.DONE) {
            const res = JSON.parse(this.responseText)
            tmp.pokemons.push({id: i, name: res.name, image: res.sprites.front_default });
            tmp.pokemons.sort(function(a, b){
              return a.id - b.id
            });
          }
        });

        xhr.open("GET", "https://pokeapi.co/api/v2/pokemon/" + i);

        xhr.send(data);
      }
    }
  },
  mounted: function() {
    this.getFewPokemons();
  }
};
</script>

<style>
table {
  background-color: gray;
  border-collapse: collapse;
  width: 40%;
  margin: auto;
}
</style>