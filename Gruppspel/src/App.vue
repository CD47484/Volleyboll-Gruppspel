<script setup>

</script>

<template>
<nav id="nav">Massor med saker</nav>

<main id="main">

<h1>Gruppspel</h1>

<button class="container">
<h3>Grupp 1</h3> <!--fetchar in grupperna-->
</button>

<button class="container">

<h3>Grupp 2 </h3> 
<p> ↓</p>
</button>
<button class="container">
<h3>Grupp 3</h3>
</button>

</main>
</template>

<style scoped>
#nav {
  position: absolute;
  display: flex;
  left: 0%;
  right: 0%;
  top: 0%;
  height: 10%;
  align-items: center;
  background-color: darkgreen;
}
#main {
  position: absolute;
  top: 10%;
  bottom: 0%;
  left: 0%;
  right: 0%;
  background-color: darkblue;
}
h3{
  color: black;
  text-align: left;
}
.container {
  position: relative;
  left: 5%;
  right: 5%;
  margin: 5%;
  height: 50px;
  width: 300px;
  align-items: center;
  background-color: white;
}
</style>
