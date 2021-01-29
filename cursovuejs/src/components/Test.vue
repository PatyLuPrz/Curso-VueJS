<template>
    <div>
        <input type="text" v-on:keyup.enter="typing">
        
    </div>
</template>

<script>
    export default {
        data(){
            return {
                titulo : 'Datos del usuario',
                user : {
                    nombre : 'Patricia',
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
        }

    }
</script>

<style media="screen">

</style>