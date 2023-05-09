<script>
export default {
  name: 'Main'
  
}
</script>

<template>
  <main>
    <div class="container">
      
      <section>1 section</section>
      <section>2 section</section>
      <section>3 section</section>
      <section>4 section</section>

    </div>

  </main>
</template>

<style lang="scss" scoped>
@import '../scss/general/variables';

main{
  min-height: 300px;
  background-color: $backgroundSecondary;
}

</style>