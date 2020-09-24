<template>
 <div>
    <ul>
        <li v-for="(user, index) in users" :key="index">
            <h4 v-if="(index >= 20 && index < 40) && (user.completed == true)">
            {{ user.title }}
            </h4>
            <p v-if="(index >= 20 && index < 40) && (user.completed == true)">
            Completo: {{user.completed}}</p>
        </li>
    </ul>
    
    <button @click="fetchUsers">Todos</button>
 </div>
</template>

<script>
export default {
 name: "Users",
    data() {
        return {
            users: [],
            baseURI: "https://jsonplaceholder.typicode.com/todos"
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