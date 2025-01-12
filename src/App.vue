<script>
export default {
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
    }
  }
}
</script>

<template>
  <div class="app">
    <h1 class="text-roboto">{{ title }}</h1>
    <p class="text-roboto">{{ info }}</p>
    <input type="text" v-model="userName" placeholder="Name" class="input"><br>
    <input type="password" v-model="userPass" placeholder="Password" class="input"><br>
    <input type="email" v-model="userMail" placeholder="Email" class="input"><br>
    <button type="button" @click="send()" class="input">Send</button>
    <p class="text-roboto" style="color: red">{{ error }}</p>
    <p class="text-roboto" v-if="users.length == 0">"users" is empty!</p>
    <p class="text-roboto" v-for="(el, index) in users" :key="index">{{ index+1 }}. {{ el.name }}: [ {{ el.mail }}, <u>{{ el.pass }}</u> ]</p>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.app {
  padding: 10px;
  background-color: rgb(241, 241, 255);
  border-radius: 5px;
}

.text-roboto {
  font-family: Roboto, Arial, Helvetica, sans-serif, system-ui;
  padding: 5px 0px;
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
  padding: 10px 0px;
  color: rgb(58, 127, 216);
  font-weight: 300;
}

p {
  color: rgb(43, 37, 37);
}
</style>
