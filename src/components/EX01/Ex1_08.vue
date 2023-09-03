<template>
  <div>
    <h1>Looping through arrays</h1>
    <ul>
      <li v-for="(item, n) in interests" :key="n">
        {{ item }}
        <ol>
          <li v-for="(fav, m) in item.favorite" :key="m">
            {{ fav }}
          </li>
        </ol>
      </li> 
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      interests: ['TV', 'Games', 'Sports'],
    }
}, }
</script>