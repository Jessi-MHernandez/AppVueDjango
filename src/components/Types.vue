<template>
    <div>
        <h5>Tipos</h5>
        <b-list-group>
                <b-list-group-item button v-for="t in types" v-bind:key="t.id">
                    <router-link :to=" '/type/' + t.id + '/elements'" >
                        {{t.title}}
                    </router-link>
                </b-list-group-item>
        </b-list-group>
    </div>
</template>



<script>
export default {
    created(){
        this.findAll()
    },
    data(){
        return{
            types: []
        };
    },
    methods: {
        findAll: function(){
            fetch('http://127.0.0.1:8000/api/type/?format=json')
            .then(res => res.json())
            //.then(res => console.log(res[1].id))
            .then(res => this.types =res)
        }
    }
};
</script>