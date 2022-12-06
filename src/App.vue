<script>
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';
  import CharactersList from './components/CharactersList.vue';
  import SingleCharacter from './components/SingleCharacter.vue';

  export default{
    components: { Header,Main,CharactersList,SingleCharacter},
    data() {
      return {
        
      }
    },
  }
  import 'bootstrap/dist/css/bootstrap.min.css'
</script>

<template>
<div>
  <Header></Header>
</div>
<div class="container">
  <CharactersList></CharactersList>
</div>
</template>

<style lang="scss">
  @use "../styles/general.scss" as * ;
</style>
