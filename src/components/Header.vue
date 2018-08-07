<template>
  <header class="header">
    <h1>{{ msg }}</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>


<style scoped>
.header {
  background: rgba(9,9,121,1);
  color: #fff;
  padding: 20px 0;

}
</style>
