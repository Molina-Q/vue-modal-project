<template>
  <h1>{{ title }}</h1>

  <div v-if="showModal">
    <Modal @close="toggleModal">
      <h1>Sign up for the Giveaway!</h1>
      <p>Grab anything you wish for!</p>

      <template v-slot:links>
        <a href="#">My biggest link</a>
        <a href="#">More info</a>
      </template>

    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>

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
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
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
