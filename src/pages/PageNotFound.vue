<template>
  <div>
    <h1>404</h1>
    <p>Page not found</p>
  </div>  
</template>

<script>
export default {
  name: 'PageNotFound'
}
</script>

<style lang="scss" scoped>
@import "@/styles/global.scss";

div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

h1 {
  font-size: 50px;
}

p {
  margin-top: 20px;
  font-size: $font18;
}
</style>