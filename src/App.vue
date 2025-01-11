<script>
export default {
  data() {
    return {
      title: 'Name of this project',
      info: 'I have some information!',
    }
  },
  methods: {
    changeText() {
      this.title = 'Tutorial';
    }
  }
}
</script>

<template>
  <div class="app">
    <h1 class="text-roboto">{{ title }}</h1>
    <p class="text-roboto">{{ info }}</p>
    <button type="button" @click="changeText()">Кликни здесь!</button>
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
}

button {
  margin: 20px 0px 10px 0px;
  padding: 5px;
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
