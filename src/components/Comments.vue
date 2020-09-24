<template>
 <div>
    <ul>
        <li v-for="(user, index) in users" :key="index">
            <h4 v-if="(user.id % 2 == 0)">
               Nome: {{user.name}} - {{user.id}}
            </h4>
            <p v-if="(user.id % 2 == 0)">E-mail: {{user.email}}</p>
            <p v-if="(user.id % 2 == 0)">Body: {{user.body}}</p>
        </li>
    </ul>
    
    <button @click="fetchUsers">Comentarios</button>
 </div>
</template>

<script>
export default {
 name: "Users",
    data() {
        return {
            users: [],
            baseURI: "https://jsonplaceholder.typicode.com/comments"
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