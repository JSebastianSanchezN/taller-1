<template>
    <h1>Octavo Punto</h1>
    <input type="number" placeholder="Ingrese el numero por el cual se va a dividir" v-model="divisor"/><br/>
    <button @click="division">Calcular division</button>
    <p>{{arreglo}}</p>
    <p>{{fin}}</p>
    <p>{{resultado}}</p>
</template>

<script>
    export default{
        name:'OctavoPunto',
        data(){
            return{
                divisor:'',
                numero:'',
                fin:'',
                arreglo:'',
                resultado:'',
                items:[],
                divididos:[]
            }
        },
        methods:{
            division(){
                this.items=Array.from({length:10},()=>Math.floor(Math.random()*10));
                if (this.divisor<0||this.divisor>this.items.length){
                    this.fin='Error, el divisor que ingreso es negativo o mayor que el arreglo'
                }else{
                    this.fin=''
                    this.numero=this.items[this.divisor]
                    for (var i=0; i<this.items.length;i++){
                        this.divididos[i]=this.items[i]/this.numero
                    }
                }
                for (var i=0;i<this.divididos.length;i++){
                    this.divididos[i]=this.divididos[i].toFixed(2);
                    this.arreglo='El arreglo es '+this.items.toString()
                    this.resultado='Y los divididos son '+this.divididos.toString()
                }
            }
        }
    }
</script>

<style scoped>
input{
    width: 300px;
}
</style>