<template>
     <input v-model="userName" type="text" placeholder="Name">
     <input v-model="userPassword" type="password" placeholder="Password">
     <input v-model="userEmail" type="email" placeholder="Email">
     <button @click="sendData">Send</button>
     <p className="error">{{error}}</p>


    <div v-if="users.length == 0">
      <h1>Not users</h1>
    </div>

    <User 
    v-for="(el, index) in users" 
    :key="index" :user="el" 
    class="box"
    :index="index"
    :deleteUser="deleteUser"
    />

    
    
</template>




<script >
import User from './components/User.vue'
 export default {
  components: {
    User,
  },



    data () {
      return {
        users: [],
        error: '',
        userName: '',
        userPassword: '',
        userEmail: '',
          
      }
    },
    methods: {
      sendData() {

        if (this.userName == '') {
            this.error = 'Имя не введено'
            return;
        } else if (this.userEmail == '') {
          this.error = 'Email не введен'
          return;
        } else if (this.userPassword == '') {
          this.error = 'Пароль не введен'
          return;
        }

        this.error = '';

        this.users.push({
          name: this.userName,
          pass: this.userPassword,
          email: this.userEmail,
        })
      },

      deleteUser(index) {
        this.users.splice(index, 1)
      }


    }
 }


</script>



<style >
  h3  { 
    font-weight: bold;
  }
  p {

    color: black;
  }
  .pone {
    color: red;
  }
  .box {
    width: 250px;
    height: 180px;
    border: 1px solid black;
    border-radius: 5px;
  }

  
</style>
