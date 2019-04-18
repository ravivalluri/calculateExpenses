<template>
  <router-view/>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
<link href="https://fonts.googleapis.com/css?family=Roboto+Slab" rel="stylesheet"/>
.col {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.col-all {
  justify-content: space-between;
  flex-grow: 3;
}

body {
  background: #0375b4;
}

.widget {
  margin: 0;
  box-sizing: border-box;
  padding: 0 5%;
  height: 100%;
}
.widget.single {
  padding: 5%;
}

.content {
  background: #ffce00;
  height: 100%;
  border: 2px solid #007849;
  border-radius: 10px;
}
.content.single {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

button {
  background: #262228;
  padding: 10px;
  border: 2px solid #0375b4;
  border-radius: 10px;
  font-size: 2.5vh;
  color: #ffce00;
}

.left {
  text-align: right;
}

.right {
  text-align: left;
  padding-left: 2vw;
}
</style>
