<template>
  <div id="index">
    <Popup v-show="showPopup" :activePlayer="activePlayer" />
    <div class="wrapp">
      <TicTac name="1" @changeActive="listen($event)" />
      <TicTac name="2" @changeActive="listen($event)" />
      <TicTac name="3" @changeActive="listen($event)" />
      <TicTac name="4" @changeActive="listen($event)" />
      <TicTac name="5" @changeActive="listen($event)" />
      <TicTac name="6" @changeActive="listen($event)" />
      <TicTac name="7" @changeActive="listen($event)" />
      <TicTac name="8" @changeActive="listen($event)" />
      <TicTac name="9" @changeActive="listen($event)" />
    </div>
  </div>
</template>

<script>
import TicTac from "./components/TicTac";
import Popup from "./components/Popup";

export default {
  name: "App",
  components: {
    TicTac,
    Popup
  },
  data() {
    return {
      activePlayer: "X",
      msg: "",
      showPopup: false,
      cells: {
        1: "",
        2: "",
        3: "",
        4: "",
        5: "",
        6: "",
        7: "",
        8: "",
        9: ""
      },
      winsRules: [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9], // rows
        [1, 4, 7],
        [2, 5, 8],
        [3, 6, 9], // columns
        [1, 5, 9],
        [3, 5, 7] // diagonals
      ]
    };
  },

  methods: {
    listen(event) {
      let _obj = this.cells;
      for (let key in _obj) {
        if (key === event) {
          _obj[key] = this.activePlayer;
        }
      }
      if (this.activePlayer === "X") {
        this.activePlayer = "0";
      } else {
        this.activePlayer = "X";
      }
    }
  },
  watch: {
    activePlayer: function checkWin() {
      let _key = Object.values(this.cells);
      //'win X'
      if (_key[0] === "X" && _key[1] === "X" && _key[2] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[3] === "X" && _key[4] === "X" && _key[5] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[6] === "X" && _key[7] === "X" && _key[8] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[0] === "X" && _key[3] === "X" && _key[6] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[1] === "X" && _key[4] === "X" && _key[7] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[2] === "X" && _key[5] === "X" && _key[8] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[0] === "X" && _key[4] === "X" && _key[8] === "X") {
        this.showPopup = true;
        console.log("win X");
      } else if (_key[2] === "X" && _key[4] === "X" && _key[6] === "X") {
        this.showPopup = true;
        console.log("win X");
      }
      //'Win 0'
      if (_key[0] === "0" && _key[1] === "0" && _key[2] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[3] === "0" && _key[4] === "0" && _key[5] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[6] === "0" && _key[7] === "0" && _key[8] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[0] === "0" && _key[3] === "0" && _key[6] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[1] === "0" && _key[4] === "0" && _key[7] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[2] === "0" && _key[5] === "0" && _key[8] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[0] === "0" && _key[4] === "0" && _key[8] === "0") {
        this.showPopup = true;
        console.log("win 0");
      } else if (_key[2] === "0" && _key[4] === "0" && _key[6] === "0") {
        this.showPopup = true;
        console.log("win 0");
      }
    }
  }
};
</script>

<style>
#index {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.wrapp {
  width: 190px;
  flex-wrap: wrap;
  display: flex;
  margin: 0 auto;
  justify-content: space-around;
}
</style>
