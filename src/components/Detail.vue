<template>
    <div>
            <b-card>
                <h2>{{element.title}}</h2>
                <div class="p-3">
                    <b-card-text>{{element.description}} </b-card-text>
                </div>
            </b-card>
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
    },
}
</script>
<style>
    .box{
        border: 2px solid #cccccc;
        margin: 2px 0 0 0;
    }
</style>