<template>
  <div>
    <PokemonBlock
      :pokemon="pokemon"
      v-for="pokemon in pokemons"
      :key="pokemon.id"
    ></PokemonBlock>
  </div>
</template>

<script>
import PokemonBlock from "components/PokemonBlock";
export default {
  computed: {
    pokemons() {
      return this.$store.state.pokemon.pokemons;
    },
  },
  components: {
    PokemonBlock,
  },
};
</script>

<style lang="scss" scoped>
</style>