<script>

</script>

<template>
  <div class="wrap">
    <h1>Weather app</h1>
    <h3>You can find out the weather in the city.</h3>
    <input type="text" placeholder="Input your city" />
    <button>Get the weather</button>
  </div>
</template>

<style scoped>
.wrap {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  padding: 20px;
  background: #1f0f24;
  text-align: center;
  color: rgb(255, 253, 216);
}

.wrap h1 {
  margin-top: 50px;
  font-family: Helvetica, Arial, Trebuchet, Tahoma, Verdana;
  font-weight: 100;
}

.wrap h3 {
  margin-top: 20px;
  font-family: Helvetica, Arial, Trebuchet, Tahoma, Verdana;
  font-weight: 100;
}

.wrap input {
  margin-top: 30px;
  background: transparent;
  border: 0px;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrap input:focus {
  border-bottom-color: #6e2d7d;
}

.wrap button {
  background: #e3bc4b;
  color: #fff;
  border-radius: 10px;
  border: 2px solid #b99935;
  padding: 10px 15px;
  margin-left: 20px;
  cursor: pointer;
  transition: transform 500ms ease;
}

.wrap button:hover {
  transform: scale(1.1) translateY(-5px);
}
</style>
