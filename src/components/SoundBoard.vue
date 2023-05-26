<template>
  <div class="soundboard">
      <h1>Interactive Animal Soundboard</h1>
      
      <div class="btns">
        <button 
          v-for="animal in animalSound"
          :key="animal.id"
          class="btn" 
          :id="animal.name"
          @click="playSound(animal.name)"
        >
          <i class="fa-solid fa-xl" :class="animal.class" :title="animal.name"></i> <!-- title is for accessibility semantic-->
        </button>
      </div>

  </div>
</template>

<script>
export default {
  name: 'SoundBoard',
  data () {
    return {
      animalSound : [
        {
          id : 0,
          name : 'bird',
          class : 'fa-crow',
        },
       
        {
          id : 1,
          name : 'cat',
          class : 'fa-cat',
        },
        {
          id : 2,
          name : 'dog',
          class : 'fa-dog',
        },
        {
          id : 3,
          name : 'cow',
          class : 'fa-cow',
        },
      ]
    }
  },
  methods: {
    playSound(animal) {
      // console.log(`${animal}.mp3`);

      const soundToPlay = new Audio(require(`../assets/sounds/${animal}.mp3`));
      soundToPlay.play();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.soundboard {
  position: absolute;
  top: 25%;
  left: 25%;
  height: 30vh;

  padding: 2rem 1rem;
 
  background-image: -webkit-linear-gradient(top, #f4f1ee, #fff);
  background-image: linear-gradient(top, #f4f1ee, #fff);
  box-shadow: 0px 8px 10px 0px rgba(21, 18, 194, 0.3), inset 0px 4px 1px 1px white, inset 0px -3px 1px 1px rgba(197, 197, 204, 0.5);

  border-radius: 5%;

  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  text-align: center;
}

.btns {
  top: 50%;
  width: 95%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  background-image: -webkit-linear-gradient(top, #eef4ef, #fff);
  background-image: linear-gradient(top, #f4f1ee, #fff);
  box-shadow: 0px 8px 10px 0px rgba(21, 18, 194, 0.3), inset 0px 4px 1px 1px white, inset 0px -3px 1px 1px rgba(197, 197, 204, 0.5);

  border-radius: 5%;
}

.btn {
  color: #054fb9;
  font-weight: bold;
  cursor: pointer; 
  border-radius: 50%;
  border: rgba(21, 18, 194, 0.3) solid 2px;;
  box-shadow: 0px 8px 10px 0px rgba(21, 18, 194, 0.3), inset 0px 4px 1px 1px white, inset 0px -3px 1px 1px rgba(197, 197, 204, 0.5);
  float:left;
  height: 70px;
  margin: 0 30px 30px 0;
  position: relative;
  width: 70px;			
  -webkit-transition: all .1s linear;
  transition: all .1s linear;
}


.btn:hover {
  color:#054fb9;
  text-shadow:0px 0px 6px #8ebbfa5e;
}

.btn:active {
  background-image: -webkit-linear-gradient(top, #efedec, #f7f4f4);
  background-image: linear-gradient(top, #efedec, #f7f4f4);
  box-shadow: 0 3px 5px 0 rgba(0,0,0,.4), inset 0px -3px 1px 1px rgba(197, 197, 204, 0.5);
}
</style>
