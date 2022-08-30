<template>
    <h1>Tercer Punto</h1>
    <input type="text" placeholder="Ingrese su nombre" v-model="nombre"/>
    <input id="hora" type="text" placeholder="Ingrese la hora en formato HH:MM con am, pm o mm si es medio dia" v-model="hora" @keypress.enter="momento" />
    <p>{{otro}}</p>
</template>

<script>
    export default {
        name:'TercerPunto',
        data() {
            return {
                nombre:"",
                hora:"",
                otro:"",
                resultado:""
            }
        },
        methods:{
            
        },
        computed:{
            momento(){
                if ((this.hora.substring(6,8))=='am'){
                    this.resultado="Buenos dias, "
                }else if ((this.hora.substring(6,8))=='pm'){
                    if((this.hora.substring(0,2))<=6){
                        this.resultado='Buenos tardes, '
                    }else{
                        this.resultado='Buenas noches, '
                    }
                }else if((this.hora.substring(6,8))=='mm'){
                    if((this.hora.substring(0,2))==12){
                        this.resultado='Buenas tardes, '
                    }else{
                        this.resultado='Algo no esta bien en la hora, '
                    }
                }
                return this.otro=this.resultado+this.nombre
            }
        }
    }
</script>

<style scoped>
input{
    width: 200px;
}
#hora{
    width: 450px;
}
</style>