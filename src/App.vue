<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <p>Welcome</p>

  <!-- orig if = showModal -->
  <div v-if="false"> 
    <!-- prop method -->
    <!-- <Modal :header="header" :text="text" @close="toggleModal"/> -->
    <Modal @close="toggleModal"> 
      <h1>This Modal</h1>
      <p>check this is modal slot</p>
      <template v-slot:links> 
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </Modal>
  </div>

  <template v-if="showModal === 1">
    
  </template>
  <button class="btn" @click="toggleModal">Modal 1</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    Modal
  },
  data() {
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for giveaway!',
      text: 'Grab your swag for half price!',
      showModal: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
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
.btn {
  padding: 10px 30px;
  margin: 0 5px;
  background-color: pink;
  border-radius: 10px;
  border: none;
  text-align: center;
  box-shadow: 0 0 0 rgba(0, 0, 0, 0.1);
  cursor: pointer;
}
.btn:hover {
  background-color: bisque;
}
</style>
