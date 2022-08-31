<template>
    <h1>Decimo Punto</h1>
    <input type="number" placeholder="Ingrese el numero de columnas" v-model="columnas"/><br/>
    <input type="number" placeholder="Ingrese el numero de filas" v-model="filas"/><br/>
    <button @click="matriz">Crear tabla</button>
    <p>{{items}}</p>
    <table border>
        <thead>
            <tr v-for="i in items.length">
                <td v-for="j in items[i-1]?.length">
                    {{i}}, {{j}}
                </td>
            </tr>
        </thead>
        <tfoot>
            <td v-for="i in columnas">
                {{suma[i-1]}}
            </td>
        </tfoot>
    </table>
    
</template>

<script>
    export default{
        name:'DecimoPunto',
        data(){
            return{
                filas:'',
                columnas:'',
                numero:0,
                suma:[],
                items:[[]]
            }
        },
        methods:{
            matriz(){
                this.items.length=this.filas
                for (var i=0;i<this.items.length;i++){
                    this.items[i]=new Array(this.columnas)
                    for (var j=0;j<this.items[i].length;j++){
                        this.items[i][j]=parseInt((Math.random())*10);
                    }
                }
                var sum=0
                for (var i=0;i<this.columnas;i++){
                    sum=0
                    for (var j=0;j<this.filas;j++){
                        sum=sum+this.items[j][i]
                    }
                    this.suma[i]=sum
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