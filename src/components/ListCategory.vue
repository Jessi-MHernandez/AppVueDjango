<template>
    <div>
        <ListDefault :elements-list="elements"/>     
        <br>
            <p class="copyright text-muted">Copyright &copy; 2020 · Jess M. Hernández (Ingeniera en Tecnologías de la Información) </p>
    </div>
  

</template>

<script>
import ListDefault from '../partials/_ListDefault'

export default {
    components:{
        ListDefault
    },


    created(){
        //console.log("Listado de categorias!!");
        this.findAll();
    },

    data(){
        return{
         
            elements: []
        };
    },
    methods: {
        findAll: function(){
            fetch('http://127.0.0.1:8000/api/category/'+this.$route.params.id+'/elements/?format=json')
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => this.elements =res)
        }
    },
    watch: {
        "$route.params.id" : function(){
            console.log("Listado de categorias!!");
            this.findAll();
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