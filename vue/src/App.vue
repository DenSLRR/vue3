<template>
     <input v-model="userName" type="text" placeholder="Name">
     <input v-model="userPassword" type="password" placeholder="Password">
     <input v-model="userEmail" type="email" placeholder="Email">

    <h2>Мое имя:{{userName}}</h2>
    <h2>Мой пароль:{{userPassword}}</h2>
    <h2>Мой маил:{{userEmail}}</h2>

</template>




<script >
import Prime from './components/Prime.vue'
 export default {
    data () {
      return {
          userName: '',
          userPassword: '',
          userEmail: '',
      }
    },
    methods: {
      

    }
 }


</script>



<style scoped>
  h3  { 
    font-weight: bold;
  }
  p {

    color: red;
  }

</style>
