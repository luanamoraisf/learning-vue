<template>
    <div>
       

        <div class="data">
            <h4>Linguagem: {{ linguagem.nome | capslkName}}</h4>
            <hr>
            <h4 v-show="2 > 1">Descrião: {{ linguagem.descricao }}</h4>
            <hr>
            <h4 v-if="showcriador == true">Criador: {{ linguagem.criador }}</h4>
            <h4 v-else>Criador Desconhecido!</h4>
            <hr>
            <h4>Ano de Criação: {{ linguagem.ano }}</h4>
            <button @click="eventDelete">Excluir</button>
        </div>
    </div>
</template>

<script>
export default{
    data() {
        return{
            
        }
    },
     props: {
        description: Number,
        showcriador: Boolean,
        linguagem: Object,
        
    }, 
    methods: {
        eventDelete: function() {
            console.log("Emitindo");
            this.$emit("deletando", {idLinguagem: this.linguagem.id});
        }
    },
    filters: {
        capslkName: function(value){
            return value.toUpperCase();
        }
    }
    
}
</script>

<style scoped>
.data{
    background-color:#6999e0; 
    width: 20%;
    padding: 1%;
    margin-top: 1%;
    margin-left: 1%;
}

</style>
