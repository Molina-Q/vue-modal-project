<template>
  <h1>{{ title }}</h1>

  <teleport to=".modals" v-if="showModal">
    <Modal @close="toggleModal">
      <h1>Sign up for the Giveaway!</h1>
      <p>Grab anything you wish for!</p>

      <template v-slot:links>
        <a href="#">My biggest link</a>
        <a href="#">More info</a>
      </template>

    </Modal>
  </teleport>

    <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Log off for the second Giveaway!</h1>
      <p>Do not grab anything!</p>

      <template v-slot:links>
        <a href="#">No link</a>
        <a href="#">Less info</a>
      </template>

    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>

  <button @click="toggleModalTwo">Open Modal Two</button>

  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
</template>

<script>

import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first vue app',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}

.active {
  background-color: yellow;
}
</style>
