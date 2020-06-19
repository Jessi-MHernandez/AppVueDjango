<template>
    <div>
        <b-container>
            <b-card :title ="element.title">
                <b-card-text>{{element.description}} </b-card-text>
            </b-card>
        </b-container>
       <!-- <button v-on:click="findAll">Haz click aqui</button>-->
    </div>
</template>

<script>
export default {
    created(){
        //console.log("Creado!!")
        this.find()
        
    },

    data(){
        return{
         
            element: Object
        };
    },
    methods: {
        find: function(){
            fetch("http://127.0.0.1:8000/api/element/"+this.$route.params.id+"/?format=json")
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => this.element =res)
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