<template>
    <div class="users">
        <h1>Componente de users</h1>
        <ul>
            <li v-for="user in users">
                {{user.nombre}} - {{user.apellido}} <button v-on:click="deleteUser(user)">Borrar</button>
            </li>
        </ul>
        <form v-on:submit.prevent='addUser'>
            <input type="text" v-model="newUser.nombre" placeholder="nombre">
            <input type="text" v-model="newUser.apellido" placeholder="apellido">
            <input type="email" v-model="newUser.email" placeholder="email">
            <button type="submit">Añadir</button>
        </form>
    </div>
</template>
<script>

export default {
    data(){
        return{
            users:[
                {
                    nombre:'Patricia',
                    apellido:'Perez',
                    email:'pato@gmail.com',
                    contacto:false,
                },
                {
                    nombre:'Daniela',
                    apellido:'Rubiales',
                    email:'dani@gmail.com',
                    contacto:true,
                },
                {
                    nombre:'Gabriela',
                    apellido:'Curiel',
                    email:'gabi@gmail.com',
                    contacto:true,
                }
            ],
            newUser:{}
        }
    },
    methods: {
        addUser(){
            this.users.push(this.newUser);
            this.newUser = {};
        },
        deleteUser(user){
            this.users.splice(this.users.indexOf(user),1);
            alert('Usuario borrado');
        },
    },
}
</script>
<style>
    .users{
        background: lightcyan;
    }
</style>