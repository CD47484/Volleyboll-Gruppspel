<script>

export default {
  name: 'App',
  data() {
    return {
      isVisible: false,
      isVisible2: false,
      isVisible3: false,
      groupAData: [
        { pos: 1, team: 'IT23', p: 5, w: 4, l: 0, pd: '61/15', pts: 13 },//Fetch in namn, hur många matcher de spelat, vunnit, förlorat, poäng för, poäng mot räknar ut poäng skillnad, poäng
        { pos: 2, team: 'Merk23', p: 5, w: 4, l: 0, pd: 61, pts: 10 },
        { pos: 3, team: 'Kock23', p: 5, w: 4, l: 0, pd: 61, pts: 7 },
        { pos: 4, team: 'Serv23', p: 5, w: 4, l: 0, pd: 61, pts: 2 },
      ],
      groupBData: [
        { pos: 1, team: 'IT22', p: 5, w: 3, l: 1, pd: 19, pts: 14 },
        { pos: 2, team: 'Merk22', p: 5, w: 4, l: 0, pd: 61, pts: 8 },
        { pos: 3, team: 'Kock22', p: 5, w: 4, l: 0, pd: 61, pts: 5 },
        { pos: 4, team: 'Serv22', p: 5, w: 4, l: 0, pd: 61, pts: 2 },
      ],
      groupCData: [
        { pos: 1, team: 'IT21', p: 5, w: 4, l: 0, pd: 61, pts: 13 },
        { pos: 2, team: 'Merk21', p: 5, w: 4, l: 0, pd: 61, pts: 10 },
        { pos: 3, team: 'Kock21', p: 5, w: 4, l: 0, pd: 61, pts: 4 },
        { pos: 4, team: 'Serv21', p: 5, w: 4, l: 0, pd: 61, pts: 1 },
      ]
    };
  },
  mounted() {
    this.populateTable('groupA', this.groupAData);
    this.populateTable('groupB', this.groupBData);
    this.populateTable('groupC', this.groupCData);
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
    populateTable(tableId, data) {
    this.$nextTick(() => {
      let tableElement = document.getElementById(tableId);
      if (!tableElement) {
        console.error(`Table with id ${tableId} not found.`);
        return;
      }
      data.forEach((rowData) => {
        let row = tableElement.insertRow();
        Object.values(rowData).forEach((cellData) => {
          let cell = row.insertCell();
          cell.textContent = cellData;
        });
      });
    });
    },
    showPopup() {
      const myPopup = new Popup({
        id: "GruppA",
        title: "Grupp A",
        content: "An example popup. Supports multiple lines.",
        CSS: `
        .popup.GruppA .popup-content {
          background-color: #ffffff;
          width: min(770px, 90vw);
          height: 95% !important;
          border-radius: 15px;
          border: 0 solid #000000;
        }`
      });
      myPopup.show();
    },
    showPopup2() {
      const myPopup2 = new Popup({
        id: "GruppB",
        title: "Grupp B",
        content: "An example popup. Supports multiple lines.",
        CSS: `
            .popup-content {
                top: 0% ;
                bottom: 0% ;
            }`
      });
      myPopup2.show();
    },
    showPopup3() {
      const myPopup3 = new Popup({
        id: "GruppC",
        title: "Grupp C",
        content: "An example popup. Supports multiple lines.",
        CSS: `
            .popup-content {
                top: 0% ;
                bottom: 0% ;
            }`
      });
      myPopup3.show();
    }
  }
}
</script>

<template>
  <nav id="nav">Massor med saker / NAV</nav>

  <main id="main">

  <div class="search-container">
    <input type="text" class="search-input" placeholder="Search..">
    <button class="search-btn">&#x1F50E</button>
  </div>

  <div>
    <button @click="toggleVisibility" class="group-container">
      <h3 class="Grupper">Grupp A</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <img class="pil" src="./assets/pngwing2.png" alt="dropdown-pil">
    </button>
    <div v-if="isVisible" class="group-dropdown">
      <table id="groupA">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupAData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
      <button @click="showPopup" class="popup-btn">Show Popup</button>
    </div>
  </div>

  <div>
    <button @click="toggleVisibility2" class="group-container">
      <h3 class="Grupper">Grupp B</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <img class="pil" src="./assets/pngwing2.png" alt="dropdown-pil">
    </button>
    <div v-if="isVisible2" class="group-dropdown">
      <table id="groupB">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupBData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
      <button @click="showPopup2" class="popup-btn">Show Popup</button>
    </div>
  </div>

  <div>
    <button @click="toggleVisibility3" class="group-container">
      <h3 class="Grupper">Grupp C</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <img class="pil" src="./assets/pngwing2.png" alt="dropdown-pil">
    </button>
    <div v-if="isVisible3" class="group-dropdown">
      <table id="groupC">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupCData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
      <button @click="showPopup3" class="popup-btn">Show Popup</button>
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
  position: relative;
  color: black;
  text-align: left;
  width: fit-content;
  font-size: 20px;
  left: 40%;
  top: 0.6em;
  width: fit-content;
}
.lag{
  position: relative;
  color: black;
  text-align: left;
  left: 20%;
  top: 1em;
  font-size: 17px;
  width: fit-content;
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
  border-radius: 10px;
  
}
.group-dropdown {
  position: relative;
  left: 5%;
  margin-left: 5%;
  margin-bottom: 5%;
  height: fit-content;
  width: 80%;
  align-items: center;
  background-color: white;
  color: black;
  border-radius: 10px;
}
.pil{
  position: relative;
  width: 40px;
  height: 30px;
  left: 39%;
  bottom: 0.8em;
  font-size: 23px;
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
  border-radius: 7px;
}
.search-btn{
  position: relative;
  right: -5.2%;
  margin: -5%;
  top: 5%;
  height: 30px;
  width: 15%;
  align-items: center;
  border-radius: 7px;
}
.popup-btn {
  position: absolute;
  margin-top: 10px;
  cursor: pointer;
  background-color: brown;
  bottom: 0%;
  align-items: center;
}

table {
  width: 100%;
  border-collapse: collapse; 
  margin: 10px;
}

th, tr {
  border-bottom: 1px solid black;
}

th:last-child, td:last-child, tr:last-child {
  border-right: none;
}
td {
  text-align: center;
}
</style>
