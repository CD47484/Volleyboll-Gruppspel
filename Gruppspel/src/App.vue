<script>

export default {
  name: 'App',
  data() {
    return {
      isVisible: false,
      isVisible2: false,
      isVisible3: false,
    };
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    },
    toggleVisibility2() {
      this.isVisible2 = !this.isVisible2;
    },
    toggleVisibility3() {
      this.isVisible3 = !this.isVisible3;
    },
  },
};

</script>

<template>
<nav id="nav">Massor med saker</nav>

<main id="main">

  <h1>Gruppspel</h1>

  <div>
    <button @click="toggleVisibility" class="container">
      <h3 class="Grupper">Grupp 1</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p> ↓</p>
    </button>
    <div v-if="isVisible">
      Hej!
    </div>
  </div>

  <div>
    <button @click="toggleVisibility2" class="container">
      <h3 class="Grupper">Grupp 1</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p> ↓</p>
    </button>
    <div v-if="isVisible2" class="">
      Hej!
    </div>
  </div>

  <div>
    <button @click="toggleVisibility3" class="container">
      <h3 class="Grupper">Grupp 1</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p> ↓</p>
    </button>
    <div v-if="isVisible3">
      Hej!
    </div>
  </div>

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
.lag{
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
.pil{
  position: relative;
  width: 50px;
  left: 80%;
  bottom: 60%;
  font-size: 25px;
}
</style>
