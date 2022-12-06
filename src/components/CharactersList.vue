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
            this.charactersList = resp.data.results;
        });
    },
};
</script>

<template>
    <div class="container">
        <div class="card" v-for="(character, index) in charactersList" :key="index">
            <ul>
                <li>
                    {{character.name}}
                    {{character.species}}
                    {{character.gender}}
                </li>
            </ul>
        </div>
    </div>
    
</template>

<style scoped lang="scss">

</style>
