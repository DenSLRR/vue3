<template>
  
    <div class="block">
          <p class="pone">{{user.name}}</p>
          <p class="pone">{{user.pass}}</p>
          <p class="pone">{{user.email}}</p>

          <button @click="deleteUser(index)">DELETE</button>
    </div>
  
</template>

<script>
  export default {
    props: {
      user: {
        type: Object,
        required: true,
      },
      index: {
        type: Number,
        required: true,
      },
      deleteUser: {
        type: Function,
        required: true,
      }
    }
  }
</script>

<style  scoped>
  .block {
    background-color: rgba(128, 128, 128, 0.349);
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    margin-bottom: 10px;
  }

  p {
    color: black;
  }
</style>