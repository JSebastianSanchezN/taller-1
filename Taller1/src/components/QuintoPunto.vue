<template>
    <h1>Quinto Punto</h1>
    <input type="number" placeholder="Ingrese el primer numero a ordenar" v-model="newPrimero"/><br/>
    <input type="number" placeholder="Ingrese el segundo numero a ordenar" v-model="newSegundo"/><br/>
    <input type="number" placeholder="Ingrese el tercer numero a ordenar" v-model="newTercero"/><br/>
    <input type="number" placeholder="Ingrese el cuarto numero a ordenar" v-model="newCuarto"/><br/>
    <button @click="organizar">Organizar</button>
    <p id="final">Los numeros ordenados de menor a mayor son {{items.toString()}}</p>
</template>

<script>
    export default{
        name:'QuintoPunto',
        data(){
            return{
                newPrimero:'',
                newSegundo:'',
                newTercero:'',
                newCuarto:'',
                items:[],
                otro:''
            }
        },
        methods:{
            organizar(){
                this.otro=this.items.splice(0,this.items.length)
                this.items.push(this.newPrimero,this.newSegundo,this.newTercero,this.newCuarto)
                this.items.sort(
                    function(a,b){
                        return a-b
                    }
                )
                final.style.visibility="visible"
            }
        }
    }
</script>

<style scoped>
input{
    width: 250px;
}
#final{
    visibility: hidden;
}
</style>