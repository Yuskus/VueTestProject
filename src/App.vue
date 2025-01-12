<script>
import User from './components/User.vue'

export default {
  components: { User },
  data() {
    return {
      title: 'Name of this project',
      info: 'I have some information!',
      error: '',
      userName: '',
      userPass: '',
      userMail: '',
      users: [] 
    }
  },
  methods: {
    send() {
      if (this.userName == '' || this.userPass == '' || this.userMail == '') {
        this.error = 'Fill in all fields!';
      }
      else {
        this.error = '';
        this.users.push({
          name: this.userName,
          pass: this.userPass,
          mail: this.userMail
        });
      }
    },
    deleteUser(index) {
      this.users.splice(index, 1);
    }
  }
}
</script>

<template>
  <div class="app">
    <h1>{{ title }}</h1>
    <p>{{ info }}</p>

    <div class="block-input">
      <input type="text" v-model="userName" placeholder="Name" class="input"><br>
      <input type="password" v-model="userPass" placeholder="Password" class="input"><br>
      <input type="email" v-model="userMail" placeholder="Email" class="input"><br>

      <button type="button" @click="send()" class="input">Send</button>

      <p style="color: red">{{ error }}</p>
    </div>

    <p v-if="users.length == 0">"users" list is empty!</p>
    <p v-else>"users" list has these elements:</p>

    <User v-for="(el, index) in users" :key="index" :user="el" :number="index+1" :deleteUser="deleteUser" />
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.block-input {
  background-color: rgb(241, 241, 255);
  border-width: 1px;
  border-radius: 5px;
  padding: 15px;
}

.app {
  background-color: rgb(218, 218, 231);
  padding: 10px;
  border-radius: 5px;
}

button {
  min-width: 70px;
  background-color: rgb(216, 234, 255);
  border-color: rgb(61, 99, 145)
}

button:hover {
  background-color: rgb(148, 195, 248);
}

.input {
  margin: 10px 0px 5px 0px;
  padding: 7px;
  border-width: 1px;
  border-radius: 5px;
}

h1 {
  padding: 15px 0px;
  color: rgb(58, 127, 216);
  font-weight: 300;
  font-family: Roboto, Arial, Helvetica, sans-serif, system-ui;
}

p {
  color: rgb(43, 37, 37);
  font-family: Roboto, Arial, Helvetica, sans-serif, system-ui;
  padding: 5px 0px;
}
</style>
