<template>
  <div class="container">
    <h1>Methods vs watchers vs computed props</h1>
    <div class="col">
      <input 
        type="text"
        placeholder="Search with method"
        v-model="input"
        @keyup="searchMethod"
        />
        <ul>
          <li v-for="(item, i) in methodFilterList" :key="i">
            {{ item }}
          </li>
        </ul>
    </div>
  </div> 
</template>

<script>
export default {
  data() {
    return {
      // Shared
      frameworkList: [
        'Vue',
        'React',
        'Backbone',
        'Ember',
        'Knockout',
        'jQuery',
        'Angular',
      ],
      // Method
      input: '',
      methodFilterList: []
    }
  },
  watch: {
    'product.price'() {
      this.discount++
    },
  },
  methods: {
    searchMethod(e) {
      this.methodFilterList = this.frameworkList.filter(
        item => item.toLowerCase().includes(this.input.toLowerCase())
      )
    }
  },
  created() {
    this.searchMethod()
  }
}
</script>
<style lang="scss" scoped>
.container {
  margin: 0 auto;
  padding: 30px;
  max-width: 600px;
 font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
.col {
  width: 33%;
  height: 100%;
  float: left;
} input {
  padding: 10px 6px;
  margin: 20px 10px 10px 0;
}
</style>