<template>
    <h1>Septimo Punto</h1>
    <input type="number" :placeholder="texto" v-model="sueldo" @keypress.enter='siguiente' /><br/>
    <button @click="calcular">Calcular sueldo</button>
    <p>{{items.toString()}}{{fin}}</p>
</template>

<script>
    export default{
        name:'SeptimoPunto',
        data(){
            return{
                sueldo:'',
                numero:2,
                texto:'Ingrese el sueldo y luego de enter',
                fin:'',
                items:[]
            }
        },
        methods:{
            siguiente(){
                this.fin=''
                this.texto='Ingrese el sueldo Nro '+this.numero  
                this.numero = this.numero+1
                this.items.push(this.sueldo)
            },
            calcular(){
                if (this.items.length==10){
                    for(var i=0;i<this.items.length;i++){
                        if(this.items[i]==''){
                            this.fin='Hay un error con los salarios, vuelva a ingresarlos'
                            this.items.length=0;
                            this.numero=1
                            this.texto='Ingrese el sueldo Nro '+this.numero 
                            this.numero = this.numero+1
                            break
                        }else{
                            this.fin=(this.items[i]*0.08)+this.items[i]
                            this.items.splice(i,1,this.fin)
                            this.fin=''
                        }
                    }
                }else{
                    this.fin='Hay un error con los salarios, hay algunos de mas o faltan algunos, vuelva a ingresar los salarios'
                    this.items.length=0;
                    this.numero=1
                    this.texto='Ingrese el sueldo Nro '+this.numero
                    this.numero = this.numero+1
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