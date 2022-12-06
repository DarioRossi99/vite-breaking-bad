<script>
import axios from "axios";
import SingleCharacter from './SingleCharacter.vue';

export default{
    name: "CharacterList",
    components:{SingleCharacter},
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

        <div class="row row-col-1 roe-col-md-4 g-4">
            <div class="col" v-for="(singlecharacter, index) in charactersList" :key="index">
                <SingleCharacter :character="singlecharacter"></SingleCharacter>
            </div>
        </div>
    </div>
    
</template>

<style scoped lang="scss">

</style>
