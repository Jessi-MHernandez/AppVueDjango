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
            fetch('http://127.0.0.1:8000/api/element/?format=json')
            .then(res => res.json())
            .then(res => console.log(res))
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