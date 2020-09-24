<template>
 <div>
    <ul>
        <li class="estilo" v-for="(user, index) in users" :key="index">
            <h4 v-if="user.id <= 5">{{ user.name }}</h4>
            <p v-if="user.id <= 5">Nome de usuário: {{user.username}}</p>
            <p v-if="user.id <= 5">E-mail: {{user.email}}</p>
            <p v-if="user.id <= 5">Rua: {{user.address.street}}</p>
            <p v-if="user.id <= 5">Suíte: {{user.address.suite}}</p>
            <p v-if="user.id <= 5">Cidade: {{user.address.city}}</p>
            <p v-if="user.id <= 5">Código postal: {{user.address.zipcode}}</p>
            <p v-if="user.id <= 5">Latitude: {{user.address.geo.lat}}</p>
            <p v-if="user.id <= 5">Longitude: {{user.address.geo.lng}}</p>
            <p v-if="user.id <= 5">Telefone: {{user.phone}}</p>
            <p v-if="user.id <= 5">Web Site: {{user.website}}</p>
            <h4 v-if="user.id <= 5">Companhia</h4>
            <p v-if="user.id <= 5">Nome: {{user.company.name}}</p>
            <p v-if="user.id <= 5">Frase de efeito: {{user.company.catchPhrase}}</p>
            <p v-if="user.id <= 5">BS: {{user.company.bs}}</p>

            
        </li>
    </ul>
    
    <button @click="fetchUsers">Fetch Users</button>
 </div>
</template>

<script>
export default {
 name: "Users",
    data() {
        return {
            users: [],
            baseURI: "https://jsonplaceholder.typicode.com/users"
     };
 },

 methods: {
    fetchUsers: function() {
        this.$http.get(this.baseURI).then((result) => {
        this.users = result.data;
        
        });
    },
  },
};
</script>
<style >

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
</style>