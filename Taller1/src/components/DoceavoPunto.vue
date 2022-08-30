<template>
    <h1>Doceavo Punto</h1>
    <input type="text" placeholder="Ingrese el nombre del estudiante" v-model="newNombre"/>
    <input type="number" placeholder="Ingrese la primera nota" v-model="newNota1"/>
    <input type="number" placeholder="Ingrese la segunda nota" v-model="newNota2"/>
    <input type="number" placeholder="Ingrese la tercera nota" v-model="newNota3"/><br/>
    <button @click="agregar">Agregar estudiante</button><br/>
    <button @click="promediar">Calcular promedio</button>
    <p id="uno">{{estudiantes}}</p>
</template>

<script>
    export default{
        name:'DoceavoPunto',
        data(){
            return{
                texto:'Ingrese la nota',
                newNota1:'',
                newNota2:'',
                newNota3:'',
                newNombre:'',
                promedio:0,
                resultado:'',
                estudiantes:[
                ]
            }
        },
        methods:{
            agregar(){
                this.estudiantes.push({
                    nombre:this.newNombre,
                    nota1:this.newNota1,
                    nota2:this.newNota2,
                    nota3:this.newNota3
                })
            },
            promediar(){
                for (var i=0;i<this.estudiantes.length;i++){
                    this.promedio=(this.estudiantes[i].nota1+this.estudiantes[i].nota2+this.estudiantes[i].nota3)/3
                    if(this.promedio<3){
                        this.resultado='Perdio la materia'
                        this.estudiantes[i].estado=this.resultado
                    }else{
                        this.resultado='Gano la materia'
                        this.estudiantes[i].estado=this.resultado
                    }
                }
                uno.style.visibility='visible'
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