<template>
    <h1>Sexto Punto</h1>
    <input type="number" placeholder="Ingrese el numero al que le quiere encontrar los menores impares" v-model="numero"/><br/>
    <button @click="mostrar">Mostrar menores impares</button>
    <p>Los menores impares de {{numero}} son {{items.toString()}}</p>
</template>

<script>
    export default{
        name:'SextoPunto',
        data(){
            return{
                numero:'',
                final:'',
                items:[]
            }
        },
        methods:{
            mostrar(){
                for (var i=0; i<this.numero;i++){
                    if((i%2)!=0){
                        this.items.push(i)
                    }
                }
            }
        }
    }
</script>

<style scoped>
input{
    width: 450px;
}
</style>