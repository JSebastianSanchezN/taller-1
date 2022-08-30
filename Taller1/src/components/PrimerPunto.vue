<template>
    <h1>Primer Punto</h1>
    <input type="number" placeholder="Ingrese una hora en segundos" v-model="sec"/>
    {{sec}}
    <button @click="Calculo">Calular</button>
    <p>{{respuesta}}</p>
</template>

<script>
    export default {
        name:'PrimerPunto',
        data() {
            return {
                sec:"",
                min:"",
                hora:"",
                sobrante:"",
                resultado:"",
                respuesta:''
            }
        },
        methods:{
            Calculo(){
                this.hora=this.sec/3600
                this.sobrante=this.sec%3600
                this.min=this.sobrante/60
                this.sobrante=this.sobrante%60
                this.respuesta=Math.trunc(this.hora)+'h:'+Math.trunc(this.min)+'m:'+Math.trunc(this.sobrante)+'s'
            }
        }
    }
</script>

<style scoped>
input{
    width: 200px;
}
</style>