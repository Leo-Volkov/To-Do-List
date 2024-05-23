<script>

export default {
  data() {
    return {
      textNote: [],
      value_inpytNote: "",
      colorNote: {
        gray: "rgba(158, 158, 158, 39%)",
        yellow: "rgba(252, 254, 158, 39%)",
        red: "rgba(255, 68, 68, 39%)",
      },
      arrColorNote: []
    }
  },
  methods: {
    addNote() {
      if (this.value_inpytNote !== "") {
        this.textNote.push(this.value_inpytNote);
        this.value_inpytNote = "";
      }
    },
    deleteNote(index) {
      this.textNote.splice(index, 1)
    }
  }
}

</script>

<template>
  <h1>To Do List</h1>

  <ul class="noteList">
    <li v-for=" (x, index) in textNote">
      <div class="Note">
        <p>{{ x }}</p>
        <div class="linia"></div>
      </div>
      <button @click="this.deleteNote(index)" class="deleteNote"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M19.6585 6.24744C20.0741 6.61112 20.1162 7.24288 19.7526 7.65852L11.0026 17.6585C10.6402 18.0726 10.0114 18.1162 9.59543 17.756L4.34543 13.2106C3.92789 12.8491 3.88247 12.2175 4.24397 11.8C4.60547 11.3825 5.23701 11.337 5.65454 11.6985L10.1525 15.5929L18.2474 6.34151C18.6111 5.92587 19.2429 5.88375 19.6585 6.24744Z" fill="black" style="fill:black;fill-opacity:1;"/>
</svg>
</button>
    </li>
  </ul>
  <div class="css-absolute-bottom">
    
    <div class="addNote">
        <div class="box_input">
        <input class="effect-16" type="text" placeholder="" v-model="this.value_inpytNote" @keyup.enter="addNote()">
        <label>Введите задачу...</label>
        <span class="focus-border"></span>
        <!-- <input type="text" placeholder="Введите задачу..." > -->
      </div>
      <button @click="addNote()"><svg width="16" height="27" viewBox="0 0 16 27" fill="none"
        xmlns="http://www.w3.org/2000/svg">
        <path
        d="M8.70711 0.292893C8.31658 -0.0976311 7.68342 -0.0976311 7.29289 0.292893L0.928932 6.65685C0.538408 7.04738 0.538408 7.68054 0.928932 8.07107C1.31946 8.46159 1.95262 8.46159 2.34315 8.07107L8 2.41421L13.6569 8.07107C14.0474 8.46159 14.6805 8.46159 15.0711 8.07107C15.4616 7.68054 15.4616 7.04738 15.0711 6.65685L8.70711 0.292893ZM9 27L9 1H7L7 27H9Z"
        fill="black" style="fill:black;fill-opacity:1;" />
      </svg>
    </button>
  </div>
</div>
<div class="blur-fon">
</div>
</template>

<style scoped>
h1 {
  text-align: center;
  font-family: "Italiana", sans-serif;
  font-size: 38px;
  font-weight: 500;
  font-style: normal;
}

.addNote {
  width: 340px;
  height: 49px;
  background-color: rgb(223, 223, 223);
  border-radius: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.addNote button {
  width: 39px;
  height: 39px;
  margin-right: 4px;
  border-radius: 50%;
  border: none;
  background-color: rgb(20, 222, 76);

  display: flex;
  justify-content: center;
  align-items: center;
}

.addNote button:hover {
  transform: scale(0.98);
  /* background-color: rgb(20, 222, 76); */
  /* box-shadow: 0 0 10px 5px rgba(221, 221, 221, 1); */
}

.addNote button:active {
  transform: scale(0.95);
  /* background-color: rgb(20, 222, 76); */
  /* box-shadow: 0 0 10px 5px rgba(221, 221, 221, 1); */
}

.addNote .box_input {
  margin-left: 15px;
}

input[type="text"] {
  font: 15px/24px 'Muli', sans-serif;
  color: #333;
  width: 273px;
  box-sizing: border-box;
  letter-spacing: 1px;
}

.effect-16 {
  border: 0;
  padding: 4px 0;
  border-bottom: 1px solid #ccc;
  background-color: transparent;
}

label {
  position: absolute;
  left: 0;
  width: 100%;
  top: 9px;
  color: #aaa;
  transition: 0.3s;
  z-index: -1;
  letter-spacing: 0.5px;
}

label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: 700;
  text-align: start;
  padding-left: 14px;
}

.focus-border {
  position: absolute;
  bottom: 0.5px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #4caf50;
  transition: 0.4s;
  margin-left: 16px;
  border-radius: 0 0px 10px 10px;
}

.effect-16:focus~.focus-border,
.has-content.effect-16~.focus-border {
  width: 91%;
  transition: 0.4s;
}

.effect-16~label {
  position: absolute;
  left: 0;
  width: 100%;
  top: 9px;
  color: #aaa;
  transition: 0.3s;
  z-index: -1;
  letter-spacing: 0.5px;
}

.effect-16:focus~label,
.has-content.effect-16~label {
  top: -16px;
  font-size: 12px;
  color: #4caf50;
  transition: 0.3s;
}

:focus {
  outline: none;
}
.blur-fon {
  width:  350px;
  height: 75px;
  position: fixed;
  bottom: 50px;
  text-align: center;
  border-radius: 500px;
  backdrop-filter: blur(1px);

  z-index: 2;
}

.css-absolute-bottom {
  width: 340px;
  height: 49px;
  /* padding: 40px; */
  position: fixed;
  bottom: 58px;
  text-align: center;
  z-index: 3;
  /* backdrop-filter: blur(5px);
  display: flex;
  justify-content: center;
  align-items: end; */
}

ul {
  list-style-type: none;
  padding: 0;
  gap: 10px;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: flex-start;
  z-index: 1;
}

li {
  width: 340px;
  min-height: 49px; 
  padding: 0 6px 0 18px;

  background-color: rgba(158, 158, 158, 39%);
  border: 0.3px solid black;
  border-radius: 27px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

li button {
  width: 38px;
  height: 38px;
  margin-right: 4px;
  border-radius: 50%;
  border: none;
  background-color: rgb(20, 222, 76);

  display: flex;
  justify-content: center;
  align-items: center;
}
li p {
  width: 260px;
  font: 15px/24px 'Muli', sans-serif;
  color: #333;
  overflow-wrap: break-word
}
</style>
