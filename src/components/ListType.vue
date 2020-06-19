<template>
    <div class="container">
        <ListDefault :elements-list="elements"/>     
    </div>
</template>

<script>
import ListDefault from '../partials/_ListDefault'

export default {
    components:{
        ListDefault
    },


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
            fetch('http://127.0.0.1:8000/api/type/'+this.$route.params.id+'/elements/?format=json')
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => this.elements =res)
        }
    },
    watch: {
        "$route.params.id" : function(){
            console.log("Listado de tipos!!");
            this.findAll();
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