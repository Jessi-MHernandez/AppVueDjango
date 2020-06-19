<template>
    <div>
            <b-card>
                <h2>{{element.title}}</h2>
                <div class="p-3" v-if="element.category">
                    <router-link class="btn btn-info btn-sm" :to="{name:'list-category', params:{id: element.category}}">{{category.title}}</router-link>
                    <router-link class="ml-2 btn btn-info btn-sm" :to="{name:'list-type', params:{id: element.type}}">{{type.title}}</router-link>

                    <b-card-text>{{element.description}} </b-card-text>
                </div>
            </b-card>
       <!-- <button v-on:click="findAll">Haz click aqui</button>-->
    </div>
</template>

<script>
const axios = require('axios');

export default {
    created(){
        //console.log("Creado!!")
        this.find()
        
    },

    data(){
        return{         
            element: Object, 
            category: Object,
            type: Object
        };
    
    },
    methods: {
        find: function(){
            fetch("http://127.0.0.1:8000/api/element/"+this.$route.params.id+"/?format=json")
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => {
                this.element =res;
                this.findCategory(this.element.category);
                this.findType(this.element.type);
            });
        },
        findCategory: function(id){
            axios.get("http://127.0.0.1:8000/api/category/"+ id +"/?format=json")
            //.then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => (this.category =res.data));
        },
        findType: function(id){
            axios.get("http://127.0.0.1:8000/api/type/"+id+"/?format=json")
            //.then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => (this.type =res.data));
        }
    }
};
</script>
<style>
    .box{
        border: 2px solid #cccccc;
        margin: 2px 0 0 0;
    }
</style>