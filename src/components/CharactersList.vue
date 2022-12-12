<script>
import axios from "axios";
import SingleCharacter from './SingleCharacter.vue';

export default{
    name: "CharacterList",
    components:{SingleCharacter},
    props:{},
    data() {
        return {
            charactersList:[],
            filters:{
                gender:"",
                species:"",
                status:"",
            }
        };
    },
    emits:["search"],
    created() {
        axios.get("https://rickandmortyapi.com/api/character")
        .then(resp =>{
            this.charactersList = resp.data.results;
        });
    },
    methods: {
        onSearchClick(){
            this.$emit("search", this.filters);

            axios.get("https://rickandmortyapi.com/api/character" , {params: this.filters})
            .then(resp =>{
            this.charactersList = resp.data.results;
        });
        }
    },
};
</script>

<template>
    <section>
        <div class="container">
            <form action="" class="mb-4" @submit.prevent="onSearchClick">
                <div class="row">
                    <div class="col-sm-6">
                        <div class="mb-3">
                            <label class="space">Gender</label>
                            <input type="text" class="from-control" name="gender" v-model="filters.gender">
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="mb-3">
                            <label class="space">Species</label>
                            <input type="text" class="from-control" name="species" v-model="filters.species">
                        </div>
                    </div>
                    <div class="col-sm-6">
                        <div class="mb-3">
                            <label class="space">Status</label>
                            <input type="text" class="from-control" name="status" v-model="filters.status">
                        </div>
                    </div>
                </div>
                <div class="d-flex gap-3 justify-content-center">
                    <button class="btn btn-secondary" type="reset">Reset</button>
                    <button class="btn btn-info">Filtra</button>
                </div>
            </form>
        </div>
    </section>
    <section>
        <div class="container">
            <div class="row row-col-4 roe-col-md-6 g-4">
                <div class="col" v-for="(singlecharacter, index) in charactersList" :key="index">
                    <SingleCharacter :character="singlecharacter"></SingleCharacter>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">

section{
    background-color: rgb(46, 58, 70);
}
.space{
    padding-right: 1rem;
}
.row{
    justify-content: center;
}

.col-sm-6{
    width: 25%;
}
.container{
    padding: 3rem;
    background-color: white;
}
</style>
