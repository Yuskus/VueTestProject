<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        },
        number: {
            type: Number,
            required: true
        },
        deleteUser: {
            type: Function,
            required: true
        }
    }
}
</script>

<template>
    <div class="block-user">
        <p>{{ number }}. {{ user.name }}: [ {{ user.mail }}, <u>{{ user.pass }}</u> ]</p>
        <button @click="deleteUser(index)">Delete</button>
    </div>
</template>

<style scoped>
.block-user {
  background-color: rgb(241, 241, 255);
  border-width: 1px;
  border-radius: 5px;
  padding: 15px;
  margin: 10px 0px;
}

p {
  color: rgb(43, 37, 37);
  font-family: Roboto, Arial, Helvetica, sans-serif, system-ui;
}

button {
  min-width: 70px;
  background-color: rgb(216, 234, 255);
  border-color: rgb(61, 99, 145);
  border-width: 1px;
  border-radius: 5px;
  padding: 7px;
}

button:hover {
  background-color: rgb(148, 195, 248);
}
</style>