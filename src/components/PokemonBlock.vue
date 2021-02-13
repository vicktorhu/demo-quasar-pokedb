<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <q-img
          :src="'pokemon/' + pokemon.id + '.jpg'"
          spinner-color="white"
          style="height: 200px; width: 200px"
        />
      </div>
    </div>
    <div class="row">
      <div class="col pokemon-name">{{ pokemon.name }}</div>
    </div>
    <div class="row">
      <div
        class="col pokemon-type-container"
        v-for="type in typeText"
        :key="type.name"
      >
        <span class="pokemon-type" :class="'bg-' + type.color">{{
          type.name
        }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    pokemon: Object,
  },
  computed: {
    types() {
      return this.$store.state.pokemon.types;
    },
    typeText() {
      let newtypes = [];
      this.pokemon.types.forEach((type) => {
        newtypes.push(this.types[type]);
      });
      return newtypes;
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  //   color: white;
  display: inline-block;
  background-color: rgb(255, 255, 255);
  margin-top: 20px;
  margin-left: 20px;
  padding: 20px;
  border-radius: 10px;
}
.pokemon-name {
  text-align: center;
  padding: 20px;
  font-size: 30px;
  color: $primary;
}
.pokemon-type {
  text-align: center;
  color: white;
  border-radius: 5px;
  display: block;
  padding: 5px;
  text-shadow: 1px 1px 5px black;
}
.pokemon-type-container {
  padding: 0 5px;
}
</style>