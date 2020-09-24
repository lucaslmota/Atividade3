<template>
 <div>
    <ul>
        <li v-for="(user, index) in users" :key="index">
            <h4 v-if="(index >= 100 && index < 150)">
                <img :src="user.url" >
            </h4>
        </li>
    </ul>
    
    <button @click="fetchUsers">Photos</button>
 </div>
</template>

<script>
export default {
 name: "Users",
    data() {
        return {
            users: [],
            baseURI: "https://jsonplaceholder.typicode.com/photos"
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