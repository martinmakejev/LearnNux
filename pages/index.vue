<template>
<div>
  <v-text-field filled outlined v-model="message"></v-text-field>
  <h1>{{reversedMessage}}</h1>
  <v-btn @mouseover="isDisabled=true" :disabled="isDisabled">Lol</v-btn>
  <v-btn @mouseover="isDisabled=false" :disabled="!isDisabled">Can't touch this</v-btn>
  <br>
  <v-text-field filled outlined v-model="newItem" @keydown.enter="addItem"></v-text-field>
  <v-btn @click="addItem">Add</v-btn>
  <ul>
    <li v-for="(item,key) in items" :key="key">{{item}}</li>
  </ul>
</div>
</template>

<script>
export default {
  data() {
    return{
      message: 'Jou vue',
      isDisabled: "true",
      newItem: "",
      items: [
        'Sai',
      ]

    }
    
  },
  computed: {
    reversedMessage(){
      return this.message.split('').reverse().join('');
    }
  },
  methods: {
    addItem(){
      if(this.newItem.trim() !== '') {
        this.items.push(this.newItem)
      }
      this.newItem = '';
    }
  }
}
</script>

<style>

</style>
