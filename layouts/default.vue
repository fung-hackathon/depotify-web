<template>
  <div id="wrapper">
    <header>
      <h1>funHacks</h1>
    </header>
    <Nuxt />
  </div>
</template>
<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
    }
  }
}
</script>
<style>
#wrapper{
  height: 100vh;
}
h1 {
  display: block;
  width: 100%;
  font-size: 2.5em;
  text-align: center;
}
header {
  margin: 0 0.5em;
}
</style>
