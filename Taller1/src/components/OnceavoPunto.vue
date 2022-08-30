<template>
    <h1>Onceavo Punto</h1>
    <input type="text" placeholder="Ingrese el nombre del estudiante" v-model="newNombre" @keypress.enter="guardar"/><br/>
    <input type="number" placeholder="Ingrese la nota" v-model="newNota" @keypress.enter="ingreso"/><br/>
    <button @click="promediar">Calcular promedio</button>
    <p id="uno">El estudiante {{estudiante.nombre}}, {{resultado}} con una nota de {{promedio.toFixed(2)}}</p><br/>
    <p>{{alerta}}</p>
</template>

<script>
    export default{
        name:'OnceavoPunto',
        data(){
            return{
                texto:'Ingrese la nota',
                numero:0,
                newNota:'',
                newNombre:'',
                promedio:0,
                alerta:'',
                resultado:'',
                estudiante:{
                    nombre:'',
                    nota:0
                }
            }
        },
        methods:{
            ingreso(){
                this.estudiante.nombre=this.newNombre
                this.estudiante.nota=this.newNota
                this.numero=this.numero+1
                if (this.numero>3){
                    this.alerta='Se ingresaron mas de tres notas, vuelva a intentarlo'
                    uno.style.visibility='hidden'
                    this.promedio=0
                    this.resultado=''
                    this.nombre=''
                    this.nota=''
                }
                this.promedio=this.promedio+this.newNota
            },
            promediar(){
                if (this.numero==3){
                    this.promedio=this.promedio/3
                    this.alerta=''
                    if(this.promedio<3){
                        this.resultado='perdio la materia'
                        uno.style.visibility='visible'
                    }else{
                        this.resultado='gano la materia'
                        uno.style.visibility='visible'
                    }
                }else{
                    this.alerta='Hacen falta notas para poder calcular el promedio'
                }               
            }
        }
    }
</script>

<style scoped>
input{
    width: 210px;
}
#uno{
    visibility: hidden;
}
</style>