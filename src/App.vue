<template>
  <h1>{{title}}</h1>

  <p>Welcome.....</p>
  
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->

     <!-- <Modal theme="sale" @close="toggleModal"/> -->

       <Modal theme="sale" @close="toggleModal">


<!-- passing a name slot -->
         <template v-slot:links>
           <a href="#">Sign Up</a>
            <a href="#">More Info</a>
         </template>

<!-- passing a Default slot -->

         <h1>Joel</h1>
         <p>Grab your data</p>
       </Modal>
    </div>

    <button @click.alt="toggleModal">Open Modal(alt)</button>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> -->
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First Vue App',
      showModal: false,
     

    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal(){

      this.showModal = !this.showModal

    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;

}
</style>
