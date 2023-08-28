<template>
  <div>
    <h1>{{isUpperCase ?  title.toUpperCase() : title }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'My first component!',
      isUpperCase: false
    }
  }
}
</script>

<style>

</style>