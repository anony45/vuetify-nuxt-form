<template>
  <div>
   <v-select label='country-code'  v-model="country" :items="itemList" item-text="name"required outlined dense color="orange"></v-select>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      countries:"",
      country:"",
      itemList: [],
      newarray:[],
    }
  },
  mounted () {
    this.getList()
  },
  
  methods: {
    getList :function () {
      axios.get('https://app.alumnipad.com/api/countries').then( response => {
        this.itemList = Object.values(response.data)
      
      }).catch(error =>{
        console.log(error.response)
      })
    },
  }
   
}
</script>

<style>

