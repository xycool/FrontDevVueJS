<template>
  <div>
    <input type="text" v-model="firstName" placeholder="First name">
    <input type="text" v-model="lastName" placeholder="Last name">
    <h3 class="output">{{ fullName }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: ''
    }
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    }
  }
}
</script>

<style>

</style>