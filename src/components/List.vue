<template>
    <div>
        <div class="box" v-for="e in elements" v-bind:key="e">
            {{e}}
        </div>

        <button v-on:click="findAll">Haz click aqui</button>

        {{msj}}
    </div>
</template>

<script>
export default {
    data(){
        return{
            msj: "... :(",
            elements: ["Uno", "Dos", "Tres"]
        };
    },
    methods: {
        findAll: function(){
            console.log("Suscribete al canal")
            this.msj = "Click :)"
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