<template>
    <h1>Sexto Punto</h1>
    <input type="number" placeholder="Ingrese el numero al que le quiere encontrar los menores impares" v-model="numero"/><br/>
    <button @click="mostrar">Mostrar menores impares</button>
    <p>{{respuesta}}</p>
</template>

<script>
    export default{
        name:'SextoPunto',
        data(){
            return{
                numero:'',
                final:'',
                items:[],
                respuesta:'',
                otro:''
            }
        },
        methods:{
            mostrar(){
                this.otro=this.items.splice(0,this.items.length)
                for (var i=0; i<this.numero;i++){
                    if((i%2)!=0){
                        this.items.push(i)
                    }
                }
                this.respuesta='Los menores impares de '+this.numero+' son '+this.items.toString()
            }
        }
    }
</script>

<style scoped>
input{
    width: 450px;
}
</style>