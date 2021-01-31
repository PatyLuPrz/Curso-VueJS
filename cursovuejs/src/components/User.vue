<template>
    <div class="users">
        <h1>Componente de users</h1>
        <ul>
            <li v-for="user in users">
                {{user.name}} - {{user.lastname}} <button v-on:click="deleteUser(user)">Borrar</button>
            </li>
        </ul>
        <form v-on:submit.prevent='addUser'>
            <input type="text" v-model="newUser.name" placeholder="nombre">
            <input type="text" v-model="newUser.lastname" placeholder="apellido">
            <input type="email" v-model="newUser.email" placeholder="email">
            <button type="submit">Añadir</button>
        </form>
    </div>
</template>
<script>

export default {
    data(){
        return{
            users:[],
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
    created() {
        this.$http.get('https://jsonplaceholder.typicode.com/users').then(res=>this.users = res.body);
    },
}
</script>
<style>
    .users{
        background: lightcyan;
    }
</style>