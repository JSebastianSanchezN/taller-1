<template>
    <h1>Segundo Punto</h1>
    <select v-model="valor">
        <option value="0">Seleccione si la llamada duro segundos o minutos</option>
        <option value="1">Segundos</option>
        <option value="2">Minutos</option>
    </select>
    <br/>
    <input type="number" placeholder="Ingrese la duracion de la llamada" v-model="duracion"/>
    {{duracion}}
    <br />
    <button @click="Calculo">Calular</button>
    <p>{{respuesta}}</p>
</template>

<script>
    export default {
        name:'SegundoPunto',
        data() {
            return {
                valor:"0",
                duracion:"",
                min:"",
                resultado:"",
                coste:"",
                respuesta:''
            }
        },
        methods:{
            Calculo(){
                if(this.valor==1){
                    this.min=this.duracion/60
                    if(this.min<=3){
                        this.coste=100
                    }else{
                        this.resultado=this.min-3
                        this.resultado=this.resultado*50
                        this.coste=100+this.resultado
                    }
                }else if(this.valor==2){
                    if(this.duracion<=3){
                        this.coste=100
                    }else{
                        this.resultado=this.duracion-3
                        this.resultado=this.resultado*50
                        this.coste=100+this.resultado
                    }
                }
                this.respuesta=this.coste+' pesos'
            }
        }
    }
</script>

<style scoped>
input{
    width: 300px;
}
</style>