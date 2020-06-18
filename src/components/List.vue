<template>
    <div>
        <div class="box" v-for="e in elements" v-bind:key="e">
            {{e}}
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            elements: ["Uno", "Dos", "Tres"]
        };
    }
}
</script>
<style>
    .box{
        border: 2px solid #cccccc;
        margin: 2px 0 0 0;
    }
</style>