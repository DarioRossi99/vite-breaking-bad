<script>
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';
  import CharactersList from './components/CharactersList.vue';
  import SingleCharacter from './components/SingleCharacter.vue';


  export default{
    components: { Header,Main,CharactersList,SingleCharacter},
    data() {
      return {
        filtersSearch:{},
      }
    },
    methods: {
      onSearch(filtersSearch){
        this.filtersSearch = filtersSearch
        
        console.log(filtersSearch);
      }
    },
  }
  import 'bootstrap/dist/css/bootstrap.min.css'
</script>

<template>
  <Header></Header>
  <CharactersList @search="onSearch"></CharactersList>
</template>

<style lang="scss">
  @use "../styles/general.scss" as * ;
</style>
