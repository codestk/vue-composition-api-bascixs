<template>
  <div class="home">
    <h2>
      {{ apptitle }}
    </h2>
    <h3>{{ counterData.title }}:</h3>
    <div>
      <button @click="minus(2)" class="btn">--</button>
      <button @click="minus(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="plus(1, $event)" class="btn">+</button>
      <button @click="plus(2)" class="btn">++</button>
    </div>
    <p>This conter is {{ oddRoEvent }}</p>
    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" v-Autofocus />
    </div>
  </div>
</template>

<script setup>
import {
  reactive,
  computed,
  watch,
  onBeforeMount,
  onMounted,
  onBeforeUnmount,
  onUnmounted,
  onActivated,
  onDeactivated,
  onBeforeUpdate,
  onUpdated,
} from "vue";

import { vAutofocus } from "@/directives/vAutofocus";

const apptitle = "Hello";
const counterData = reactive({
  count: 0,
  title: "My couinter z",
});

const plus = (amount, e) => {
  console.log(e);
  counterData.count = counterData.count + amount;
};
const minus = (amount) => {
  counterData.count = counterData.count - amount;
};

//Vue Function
watch(
  () => counterData.count,
  (newCount, OleCount) => {
    console.log("newCount", newCount);
    console.log("OleCount", OleCount);
  }
);

const oddRoEvent = computed(() => {
  if (counterData.count % 2 === 0) return "even";

  return "odd";
});

/*
 directive
*/

//v-AutoFocus on the template

//-------------Event
// onUnmounted(() => {
//   console.log("onUnmounted");
// });

// onBeforeMount(() => {
//   console.log("onBeforeMount");
// });

// onBeforeUnmount(() => {
//   console.log("onBeforeUnmount");
// });

// onDeactivated(() => {
//   console.log("onDeactivated");
// });
// onBeforeUpdate(() => {
//   console.log("onBeforeUpdate");
// });

// onUpdated(() => {
//   console.log("onUpdated");
// });
</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn,
.counter {
  font-size: 40px;
  margin: 20px;
}

.edit {
  margin: 20px;
}
</style>
