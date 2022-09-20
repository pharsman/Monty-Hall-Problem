<template>
  <!-- <div @click="revOne" class="cont">
    <button>Door</button>
    <div>
      <h2 v-if="show1">{{goat}}</h2>
    </div>
  </div>
  <div @click="revTwo" class="cont">
    <button>Door</button>
    <div>
      <h2 v-if="show2">{{goat}}</h2>
    </div>
  </div>
  <div @click="revThree" class="cont">
    <button>Door</button>
    <div>
      <h2 v-if="show3">{{car}}</h2>
    </div>
  </div> -->
  <!-- <button @click="randomize">Click</button> -->
  <!-- <h1>{{randomPrize}}</h1>
  <h1>{{randomPrize}}</h1>
  <h1>{{randomPrize}}</h1> -->
  <div class="wall">
    <Door v-for="prize in prizes" :key="prize.id" :id="prize.id" @open="open" :randomPrize="prize.text"
      :isOpen="isOpen" />
  </div>
  <!-- 🐏 -->
  <!-- 🚗 -->
</template>

<script setup>
import Door from './components/Door.vue';
import { ref, computed } from 'vue'

// const goat = ref('🐏')
// const car = ref('')

const randomPrize = computed(() => {
  return randomPrize.value = prizes.value[Math.floor(Math.random() * (prize.value.length))]
})

const prizes = ref({
  goatOne: {
    id: 1,
    text: '🐏'
  },
  goatTwo: {
    id: 2,
    text: '🐏'
  },
  car: {
    id: 3,
    text: '🚗'
  }

})

const isOpen = ref(false)

const isDoorOpen = computed((prizeId) => {
  return prizes.value = prizes.value.filter(prize => prize.id === prizeId)
})

const open = () => {
  isOpen.value = !isOpen.value
}


// const randomize = () => {
//   randomPrize.value = prize.value[Math.floor(Math.random() * (prize.value.length))]
// }



// const show1 = ref(true)
// const show2 = ref(true)
// const show3 = ref(true)


// const revOne = () => {
//   show1.value = !show1.value
// }
// const revTwo = () => {
//   show2.value = !show2.value
// }
// const revThree = () => {
//   show3.value = !show3.value
// }



</script>

<style>
/* body {
  padding: 50px;
}

div {
  width: 50px;
  height: 50px;
}

.cont {
  display: flex;

}

h2 {
  margin-top: 14px;
  margin-left: 10px;
}

button {
  background-color: aqua;
  cursor: pointer;
  margin-top: 20px;
} */
h2 {
  text-align: center;
  margin: 50px;
  font-size: 50px;
}

body {
  height: 100%;
}

.wall {
  display: flex;
}
</style>