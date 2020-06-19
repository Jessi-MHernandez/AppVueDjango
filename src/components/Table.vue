<template>
    <div>
        <b-container>
            <b-table hover :items="elements" :fields="fields">

            </b-table>
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
            fields:[
                {
                    key: 'id',
                    sortable: true
                },
                {
                    key: 'title',
                    sortable: false
                },
                {
                    key: 'url_clean',
                    sortable: true,
                    variant: 'warning'
                },
                {
                    key: 'description',
                    sortable: true
                },
                {
                    key: 'category',
                    sortable: true
                },
                {
                    key: 'type',
                    sortable: true
                }

            ],
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