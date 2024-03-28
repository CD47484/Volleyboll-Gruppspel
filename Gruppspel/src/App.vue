<script>

export default {
  name: 'App',
  data() {
    return {
      isVisible: false,
      isVisible2: false,
      isVisible3: false,
      groupAData: [
        { pos: 1, team: 'IT23', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 13 },//Fetch in namn, hur många matcher de spelat, vunnit, förlorat, poäng för, poäng mot räknar ut poäng skillnad, poäng
        { pos: 2, team: 'Merk23', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 10 },
        { pos: 3, team: 'Kock23', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 7 },
        { pos: 4, team: 'Serv23', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 2 },
      ],
      groupBData: [
        { pos: 1, team: 'IT22', p: 5, w: 3, l: 1, pf: 160, pa: 99, pd: 19, pts: 14 },
        { pos: 2, team: 'Merk22', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 8 },
        { pos: 3, team: 'Kock22', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 5 },
        { pos: 4, team: 'Serv22', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 2 },
      ],
      groupCData: [
        { pos: 1, team: 'IT21', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 13 },
        { pos: 2, team: 'Merk21', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 10 },
        { pos: 3, team: 'Kock21', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 4 },
        { pos: 4, team: 'Serv21', p: 5, w: 4, l: 0, pf: 160, pa: 99, pd: 61, pts: 1 },
      ]
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
    mounted() {
    this.populateTable('groupA', this.groupAData);
    this.populateTable('groupB', this.groupBData);
    this.populateTable('groupC', this.groupCData);
  },
  methods: {
    populateTable(tableId, data) {
      // Use Vue's nextTick to ensure the DOM has updated and to access the updated this.$el
      this.$nextTick(() => {
        let table = this.$el.querySelector(`#${tableId}`);
        if (table) {
          data.forEach((rowData) => {
            let row = table.insertRow(-1);
            Object.values(rowData).forEach((cellData) => {
              let cell = row.insertCell();
              cell.textContent = cellData;
            });
          });
        }
      });
    },
  },
},
};

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
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible" class="group-dropdown">
      <table id="groupA">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PF</th>
          <th>PM</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupAData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pf }}</td>
          <td>{{ item.pa }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
    </div>
  </div>

  <div>
    <button @click="toggleVisibility2" class="group-container">
      <h3 class="Grupper">Grupp 2</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible2" class="group-dropdown">
      <table id="groupB">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PF</th>
          <th>PM</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupBData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pf }}</td>
          <td>{{ item.pa }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
    </div>
  </div>

  <div>
    <button @click="toggleVisibility3" class="group-container">
      <h3 class="Grupper">Grupp 3</h3> <!--fetchar in grupperna-->
      <p class="lag">IT21, IT23, IT22, IT24</p> <!--fetchar in lagen-->
      <p class="pil"> ↓</p>
    </button>
    <div v-if="isVisible3" class="group-dropdown">
      <table id="groupB">
        <tr>
          <th>POS</th>
          <th>LAG</th>
          <th>S</th>
          <th>V</th>
          <th>F</th>
          <th>PF</th>
          <th>PM</th>
          <th>PS</th>
          <th>POÄ</th>
        </tr>
        <tr v-for="item in groupBData" :key="item.pos">
          <td>{{ item.pos }}</td>
          <td>{{ item.team }}</td>
          <td>{{ item.p }}</td>
          <td>{{ item.w }}</td>
          <td>{{ item.l }}</td>
          <td>{{ item.pf }}</td>
          <td>{{ item.pa }}</td>
          <td>{{ item.pd }}</td>
          <td>{{ item.pts }}</td>
        </tr>
      </table>
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
  width: fit-content;
}
.lag{
  position: relative;
  color: black;
  text-align: left;
  top: 0.6em;
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
}
.pil{
  position: relative;
  width: 50px;
  left: 80%;
  bottom: 0.8em;
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
  right: -5.2%;
  margin: -5%;
  top: 5%;
  height: 30px;
  width: 15%;
  align-items: center;
}

/* Apply border to the table and its cells */
table {
  width: 100%;
  border-collapse: collapse; /* Collapses borders between table cells */
}

/* Apply horizontal border to table header and table rows */
th, tr {
  border-bottom: 1px solid black;
}

/* Remove right border from the last header cell and last data cell in each row */
th:last-child, td:last-child, tr:last-child {
  border-right: none;
}

</style>
