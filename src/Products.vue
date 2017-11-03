<template>
    <div>
        <ul>
            <li v-for="proizvod in lista_proizvoda">{{ proizvod }}</li>
        </ul>
        <p>{{neki_objekt.ime}} {{neki_objekt.prezime}}</p>
        <div>
                <p>{{ulazni_string}}</p>
        </div>
        <button v-on:click="button1_Clicked">Pročitaj objekat</button>
    </div>
</template>
<script>
    export default{
        props:{
            lista_proizvoda: {
                type: Array,
                required: true
            },
            neki_objekt: {
                type: Object,
                required: true
            },
            ulazni_string: {
                type: String
            }
        },
        data() {
            return {
            }
        },
        methods:{
            button1_Clicked(){
                console.log(this.neki_objekt);
                this.neki_objekt.ime="Nikola";
            }
        },
        created(){
            
        }
    }
</script>