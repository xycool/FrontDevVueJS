<template>
  <div>
    <div>
      <input 
        id="iptItem" 
        placeholder="press enter to add new item." 
        type="text" 
        @keyup.enter="addItem(shopItem)"
        v-model="shopItem">
      <button @click="addItem(shopItem)">Add Item</button>
    </div>
    <div>
      <ul>
        <li v-for="(item, n) in shopList" :key="n">
          {{ item }} <a href="#" @click="deleteItem(item)">Remove</a>
        </li> 
      </ul>
    </div>
    <div>
      <button @click="deleteAll()">Delete All</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shopList: [],
      shopItem: ''
    }
  },
  methods: {
    addItem(item) {
      if (item) {
        this.shopList.push(item)
        this.shopItem = ''
      }
    },
    deleteItem(value) {
      this.shopList = this.shopList.filter(item => item != value)
    },
    deleteAll() {
      if (confirm('Are you sure?')) {
        this.shopList = []
      }
    }
  }
}
</script>

<style>

</style>