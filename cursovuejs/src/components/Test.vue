/* eslint-disable */
<template>
    <div>
        {{ fullname }}
        
    </div>
</template>

<script>
    export default {
        data(){
            return {
                titulo : 'Datos del usuario',
                user : {
                    nombre : 'Patricia',
                    apellido : 'Perez',
                    email : 'may.patrics@gmail.com',
                },
                showName : true,
                perros : [
                    {nombre : 'loveless' , edad : '3'},
                    {nombre: 'dolly' , edad : '13'},
                ]
            }
        },
        methods:{
            saludar (nombre) {
                alert('Holis! ' + nombre);
            },
            typing (e) {
                console.log(e.target.value);
            },
        },
        computed:{
            fullname(){
                return this.user.nombre + ' ' + this.user.apellido;
            }
        },

    }
</script>

<style media="screen">

</style>