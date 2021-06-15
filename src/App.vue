<template>
  <h1>{{title}}</h1>

  <p>Welcome.....</p>
  
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->

     <!-- <Modal theme="sale" @close="toggleModal"/> -->

     <!-- https://youtu.be/KM1U6DqZf8M?list=PL4cUxeGkcC9hYYGbV60Vq3IXYNfDk8At1 -->

       <Modal theme="" @close="toggleModal">


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





  <div v-if="showModalTwo">
       <Modal @close="toggleModalTwo">
         <h1>Sign Up To The News Letter</h1>
         <p>For Update and Promo Codes</p>
       </Modal>
    </div>
    <button @click.alt="toggleModal">Open Modal(alt)</button>

    <button @click="toggleModalTwo">Open Modal Two</button>
  
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
       showModalTwo: false,
     

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

    },


     toggleModalTwo(){

      this.showModalTwo = !this.showModalTwo

    },

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
