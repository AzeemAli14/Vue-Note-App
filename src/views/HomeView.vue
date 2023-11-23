<template>
  <div
    class="border-double border-4 my-6 border-green-700 rounded-xl text-center"
  >
    <h1 class="text-2xl text-[#41b883] bg-[#34495e] font-bold">Routes</h1>
    <ul
      class="flex text-center justify-center gap-5 border-double rounded-md bg-[#41b883] py-4"
    >
      <li v-for="post in posts" :key="post.id">
        <RouterLink
          :to="{ name: 'post', params: { id: post.id } }"
          class="font-bold hover:text-white text-xl text-green-700 text-bold"
          >{{ post.title }}</RouterLink
        >
      </li>
    </ul>
  </div>

  <h1 class="appTitle">{{ appTitle }}</h1>

  <div class="home">
    <button @click="decrement(2)" class="btn">--</button>
    <button @click="decrement(1)" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="increment(1)" class="btn">+</button>
    <button @click="increment(2)" class="btn">++</button>
    <div class="computed">
      <p>This number is: {{ computedNum }}</p>
    </div>

    <div class="title">
      <h4>Change Title:</h4>
      <input
        class="text-black rounded-xl px-3 border-double border-4 border-[#41b883] my-4"
        type="text"
        v-focus="vFocus"
        v-model="counterData.modTitle"
      />
    </div>
  </div>
  <h1 class="title">{{ counterData.modTitle }}</h1>
</template>

<!-- Compsition API -->
<script setup>
// imports
import {
  nextTick,
  ref,
  reactive,
  computed,
  watch,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  onActivated,
  onDeactivated,
} from "vue";
import { vFocus } from "@/directives/vFocus.js";
// Non-Reactive Value {{**App Title**}}
const appTitle = "Vue Counter App";

//  Using refs
// const count = ref(0)
// const modTitle = ref('Change Title')

//  Using reactive Value {**Couter**}
const counterData = reactive({
  count: 0,
  modTitle: "Customize Title",
});

const increment = (amount) => {
  counterData.count += amount;
  nextTick(() => {
    if (counterData.count ++ ) {
      alert("Counter Incremented");
    }
  })
};

const decrement = (amount) => {
  counterData.count -= amount;
  nextTick(() => {
    if (counterData.count -- ) {
      alert("Counter Decremented");
    }
  })
};

// Computed Value
const computedNum = computed(() => {
  if (counterData.count % 2 === 0) {
    return "Even";
  } else {
    return "Odd";
  }
});

// watch Value
watch(
  () => counterData.count,
  (newVal, oldVal) => {
    if (newVal === 10) {
      alert("10 reached ... Hoorah!");
    }
  }
);

// Lifecycle Hooks
onBeforeMount(() => {
  console.log("onBeforeMount");
}),
  onMounted(() => {
    console.log("onMounted");
  });

onBeforeUpdate(() => {
  console.log("onBeforeUpdate");
});

onUpdated(() => {
  console.log("onUpdated");
});

onBeforeUnmount(() => {
  console.log("onBeforeUnmount");
});

onUnmounted(() => {
  console.log("onUnmounted");
});

onActivated(() => {
  console.log("onActivated");
});

onDeactivated(() => {
  console.log("onDeactivated");
});

//Posts
const posts = ref([
  {
    id: 'id1',
    title: "Post 1",
  },
  {
    id: 'id2',
    title: "Post 2",
  },
  {
    id: 'id3',
    title: "Post 3",
  },
]);
</script>

// export default { // setup() { // const count = ref(0) // const increment = ()
=> { // count.value++ // } // const decrement = () => { // count.value-- // } //
return { // count, // increment, // decrement // } // } // }

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

.title,
.computed {
  margin-top: 20px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  text-align: center;
}

.appTitle {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 50px;
  margin-top: 30px;
  text-align: center;
}

.text :focus {
  background-color: #41b883;
}
</style>
