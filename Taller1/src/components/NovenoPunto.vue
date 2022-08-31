<template>
    <h1>Noveno Punto</h1>
    <input type="number" placeholder="Ingrese el numero de columnas" v-model="columnas"/><br/>
    <input type="number" placeholder="Ingrese el numero de filas" v-model="filas"/><br/>
    <button @click="matriz">Crear tabla</button>
    <p>{{items.toString()}}</p>
    <table border>
        <thead>
            <tr v-for="i in items.length">
                <td v-for="j in items[i-1]?.length">
                    {{i}}, {{j}}
                </td>
            </tr>
        </thead>
    </table>
</template>

<script>
    export default{
        name:'NovenoPunto',
        data(){
            return{
                filas:'',
                columnas:'',
                numero:0,
                items:[]
            }
        },
        methods:{
            matriz(){
                this.items.length=this.columnas
                for (var i=0;i<this.items.length;i++){
                    this.items[i]=new Array(this.filas)
                    for (var j=0;j<this.items[i].length;j++){
                        this.items[i][j]=parseInt((Math.random())*10);
                    }
                }
            }
        }
    }
</script>

<style scoped>
input{
    width: 210px;
    
}
</style>