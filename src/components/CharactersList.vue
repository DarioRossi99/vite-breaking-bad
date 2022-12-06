<script>
import axios from "axios";

export default{
    name: "CharacterList",
    props:{},
    data() {
        return {
            charactersList:[]
        };
    },
    created() {
        axios.get("https://rickandmortyapi.com/api/character")
        .then(resp =>{
            this.characterList = resp.data.results;
        });
    },
};
</script>

<template>
    <div class="container">
        <ul>
            <li v-for="(character, index) in charactersList" :key="index">
                {{character.name}}
            </li>
        </ul>
    </div>
    
</template>

<style scoped lang="scss">

</style>
