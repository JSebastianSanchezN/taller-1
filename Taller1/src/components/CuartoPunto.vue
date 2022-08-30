<template>
    <h1>Cuarto Punto</h1>
    <input type="number" placeholder="Ingrese el primer numero a comparar" v-model="primero"/><br/>
    <input type="number" placeholder="Ingrese el segundo numero a comparar" v-model="segundo"/><br/>
    <input type="number" placeholder="Ingrese el tercer numero a comparar" v-model="tercero"/><br/>
    <button @click="comparar">Comparar</button>
    <p id="para">La cantidad de numeros iguales es de {{resultado}}</p>
</template>

<script>
    export default{
        name:'CuartoPunto',
        data(){
            return{
                primero:"",
                segundo:"",
                tercero:"",
                resultado:""
            }
        },
        methods:{
            comparar(){
                this.resultado=0
                if(this.primero==this.segundo && this.segundo==this.tercero){
                    this.resultado=3
                }else if(this.primero==this.segundo||this.segundo==this.tercero||this.primero==this.tercero){
                    this.resultado=2
                }
                para.style.visibility = "visible";
            }
        }
    }
</script>

<style scoped>
input{
    width: 250px;
}
#para{
    visibility:hidden;
}
</style>