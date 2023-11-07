<template>

  <h1 class="appTitle">{{ appTitle }}</h1>

  <div class="home">
    <button @click="decrement(2)" class="btn">--</button>
    <button @click="decrement(1)" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="increment(1)" class="btn">+</button>
    <button @click="increment(2)" class="btn">++</button>
    
    <div class="title">
      <h4>Change Title:</h4>
      <input type="text" v-model="counterData.modTitle">
    </div>
  </div>
  <h1 class="title">{{ counterData.modTitle }}</h1>
</template>

<!-- Compsition API -->
<script setup>
import { ref, reactive } from 'vue';

// Non-Reactive Value
const appTitle = 'Vue Counter App'

//  Using refs
// const count = ref(0)
// const modTitle = ref('Change Title')

const counterData = reactive({
  count: 0,
  modTitle: 'Customize Title'
})

    const increment = (amount) => {
      counterData.count += amount
    }

    const decrement = (amount) => {
      counterData.count -= amount
    }
</script>

// export default {
//   setup() {
//     const count = ref(0)

//     const increment = () => {
//       count.value++
//     }

//     const decrement = () => {
//       count.value--
//     }

//     return {
//       count,
//       increment,
//       decrement
//     }
//   }
// }


<!-- Option API -->
<!-- <script>
// export default {
//   data() {
//     return {
//       count: 0
//     }
//   },
//   methods: {
//     increment() {
//       this.count++
//     },
//     decrement() {
//       this.count--
//     }
//   }
// }
</script> -->

<style scoped>
.home {
  padding: 2px;
  margin-top: 30px;
  text-align: center;
}

.btn,
.counter {
  font-size: 40px;
  margin: 10px;
}

.title {
  margin-top: 40px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  text-align: center;
}

.appTitle {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 50px;
  margin-top: 30px;
  text-align: center;
}

</style>
