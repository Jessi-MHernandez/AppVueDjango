<template>
    <div>
        <b-container>
            <router-link to="/detail">Detalles</router-link>

        <div v-for="e in elements" v-bind:key="e.id">
            <router-link :to=" '/detail/' + e.id " >
                <b-card
                    :title ="e.title"
                >
            
                <b-card-text>
                    {{e.description}}
                </b-card-text>
                </b-card>
            </router-link>
 
        </div>
        </b-container>

       <!-- <button v-on:click="findAll">Haz click aqui</button>-->

    </div>
</template>

<script>
export default {
    created(){
        //console.log("Creado!!")
        this.findAll()
    },

    data(){
        return{
         
            elements: []
        };
    },
    methods: {
        findAll: function(){
            fetch('http://127.0.0.1:8000/api/element/?format=json')
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => this.elements =res)
        }
    }
}
</script>
<style>
    .box{
        border: 2px solid #cccccc;
        margin: 2px 0 0 0;
    }
</style>