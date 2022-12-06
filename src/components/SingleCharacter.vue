<script>

export default{
    name:"SingleCharacter",
    props:{
        /**
         * @property {string} name
         * @property {string} gender
         * @property {string} status
         * @property {string} species
         */
        character: {
            type: Object,
            required:true
        }
    },
    data() {
        return {
        };
    },
    methods: {
        
    },
};
</script>

<template>
  <section>
    <div class="card">
        <img class="card-img-top" :src="character.image" :alt="('Card image di' + character.name)" >
        <div class="card-body">
        <h5 class="card-title">{{character.name}}</h5>
        <p class="card-text">{{character.gender}}</p>
        <p class="card-text">{{character.species}}</p>
        <p class="card-text">{{character.status}}</p>
  </div>
</div>
  </section>
</template>

<style scoped lang="scss">
@use "../styles/general.scss" as * ;

</style>
