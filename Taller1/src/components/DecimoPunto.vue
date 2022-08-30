<template>
    <h1>Decimo Punto</h1>
    <input type="number" placeholder="Ingrese el numero de columnas" v-model="columnas"/><br/>
    <input type="number" placeholder="Ingrese el numero de filas" v-model="filas"/><br/>
    <button @click="matriz">Crear tabla</button>
    <p>{{items.toString()}}</p>
</template>

<script>
    export default{
        name:'DecimoPunto',
        data(){
            return{
                filas:'',
                columnas:'',
                numero:0,
                suma:0,
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
                document.writeln('<table border>')
                document.writeln('<thead>')
                for (i=0;i<this.columnas+1;i++){
                    document.writeln("<th>")
                    document.writeln(this.numero)
                    this.numero=this.numero+1
                    document.writeln("</th>")
                }
                document.writeln('</thead>')
                this.numero=1
                for (i=0;i<this.filas;i++){
                    document.writeln("<tr>")
                    document.writeln("<th>")
                    document.writeln(this.numero)
                    this.numero=this.numero+1
                    document.writeln("</th>")
                    for (j=0;j<this.columnas;j++){
                        document.writeln("<td>")
                        document.writeln(this.items[j][i])
                        document.writeln("</td>")
                    }
                    document.writeln("</tr>")
                }
                document.writeln("<tfoot>")
                document.writeln("<td>")
                document.writeln('Total')
                document.writeln("</td>")
                for (i=0;i<this.columnas;i++){
                    this.suma=0
                    document.writeln("<td>")
                    for (j=0;j<this.filas;j++){
                        this.suma=this.suma+this.items[i][j]
                    }
                    document.writeln(this.suma)
                    document.writeln("</td>")
                }
                document.writeln("</tfoot>")
                document.writeln("</table>")
            }
        }
    }
</script>

<style scoped>
input{
    width: 210px;
    
}
</style>