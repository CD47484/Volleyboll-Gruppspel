<script setup>

</script>

<template>
<nav id="nav">Massor med saker</nav>

<main id="main">
  
<h1>Gruppspel</h1>

<button class="container">
<h3 class="Grupper">Grupp 1</h3> <!--fetchar in grupperna-->
<p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
</button>

<button class="container">
<h3 class="Grupper">Grupp 2</h3>
<p class="lag">IT21, IT23, IT22, IT24</p> 
</button>

<button class="container">
<h3 class="Grupper">Grupp 3</h3>
<p class="lag">IT21, IT23, IT22, IT24</p>
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
.Grupper{
  color: black;
  text-align: left;
}
.Lag{
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
