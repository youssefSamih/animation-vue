<script setup>
import { ref, Transition } from 'vue'

// const showGreet = ref(true)
const names = ref(['Selena Damo', 'John Doe', 'Jane Doe'])
const nameInput = ref('')

function addInvitee() {
  names.value.unshift(nameInput.value)
  nameInput.value = ''
}
</script>

<template>
  <main>
    <!-- <div class="container">
      <Transition name="fade">
        <h1 v-if="showGreet">Hello world</h1>
        <h1 v-else>Goodbye world</h1>
      </Transition>
    </div> 
    <button @click="showGreet = !showGreet">Toggle</button> -->

    <div class="container">
      <input type="text" placeholder="Person to invite..." v-model="nameInput" @keypress.enter="addInvitee">

      <ul>
        <li v-for="name in names" :key="name">{{ name }}</li>
      </ul>
    </div>
  </main>
</template>

<style>
/* .fade-enter-from {
  opacity: 0;
}

 .fade-enter-to {
  opacity: 1;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease;
}

.fade-leave-from {
  opacity: 1;
} 

.fade-leave-to {
  opacity: 0;
}

.container {
  position: relative;
}

h1 {
  position: absolute;
}

button {
  margin-top: 50px;
}*/

.container {
  max-width: 300px;
  margin: 20px auto;
}

.container input {
  width: 100%;
  border-radius: 5px;
  border: 1px solid rgba(128, 128, 128, 0.13);
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12);
}

ul {
  display: inline;
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  list-style: none;
  width: 300px;
  border-radius: 5px;
  padding: 5px 10px;
  margin-top: 10px;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.12);
  text-align: center;
  cursor: pointer;
}
</style>
