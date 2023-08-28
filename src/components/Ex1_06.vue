<template>
  <div>
    <h1 v-show="true" v-once v-text="text"></h1>
    <h2 v-show="false" v-html="html" />
    <a 
    :href="link.url"
    :target="link.target"
    :tabindex="link.tabindex"
    v-text="link.title"
    ></a>
  </div>
</template>
<script>
export default {
  data() {
    return {
// v-text
      text: 'Directive text',
      html: 'Stylise</br>HTML in<br/><b>your data</b>',
      // v-bind
      link: {
        url: "https://google.com",
        target: "_blank",
        tabindex: "0",
        title: "Go to Google",
      },
    }
}, }
</script>
<style lang="scss" scoped>
h2 {
  margin: 40px 0 0;
  font-weight: normal;
}
</style>