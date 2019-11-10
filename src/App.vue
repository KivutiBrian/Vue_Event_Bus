<template>
  <div id="app">
   
    <Header />

    <div class="container mt-5">
      <div class="row">
        <div class="col-md-6">
          <Info :message="message" @Changename="message = $event"/>
        </div>
        <div class="col-md-6">
          <Details />
          
        </div>
      </div>

    </div>

  </div>
</template>

<script>

import Header from './components/header/Header.vue'
import Info from './components/User/Info.vue'
import Details from './components/User/Details'

export default {
  name: 'app',
  components: {
    Header,
    Info,
    Details
  },
  data(){
    return {
      message: 'I love vue js'
    }
  },

  methods:{
    updateMessage(value){
      this.message = value
    }
  }
}
</script>

<style>

</style>
