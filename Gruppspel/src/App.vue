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
  <nav id="nav">Massor med saker / NAV</nav>

  <main id="main">

  <div class="search-container">
    <input type="text" class="search-input" placeholder="Search..">
    <button class="search-btn"></button>
  </div>

  <div>
    <button @click="toggleVisibility" class="group-container">
      <h3 class="Grupper">Grupp 1</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible" class="group-dropdown">
      Hej!
    </div>
  </div>

  <div>
    <button @click="toggleVisibility2" class="group-container">
      <h3 class="Grupper">Grupp 2</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible2" class="group-dropdown">
      Hej!
    </div>
  </div>

  <div>
    <button @click="toggleVisibility3" class="group-container">
      <h3 class="Grupper">Grupp 3</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible3" class="group-dropdown">
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
  width: fit-content;
  font-size: 20px;
}
.lag{
  position: relative;
  color: black;
  text-align: left;
}
.group-container {
  position: relative;
  left: 5%;
  margin: 5%;
  margin-bottom: 1.5%;
  height: 10%;
  width: 80%;
  align-items: center;
  background-color: white;
}
.group-dropdown {
  position: relative;
  left: 5%;
  margin-left: 5%;
  margin-bottom: 5%;
  height: 75px;
  width: 80%;
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
.search-container {
  position: relative;
  left: 5%;
  right: 5%;
  margin: 5%;
  height: 20px;
  width: 80%;
  align-items: center;
}
.search-input{
  position: relative;
  right: -5%;
  margin: 5%;
  height: 30px;
  width: 70%;
  align-items: center;
}
.search-btn{
  position: relative;
  right: 5%;
  margin: -5%;
  top: 35%;
  height: 30px;
  width: 15%;
  align-items: center;
}

</style>
