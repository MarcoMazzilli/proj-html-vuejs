<script>
import AboutUs from './MicroComponents/main-section/AboutUs.vue';
import ChooseUs from './MicroComponents/main-section/Choose-us.vue';
import ReviewERating from './MicroComponents/main-section/Review-e-rating.vue';
import Service from './MicroComponents/main-section/Service.vue';



export default {
    name: "Main",
    components: { 
      AboutUs, 
      ChooseUs, 
      ReviewERating, 
      Service }
}
</script>

<template>
  <main>
      
      <AboutUs />

      <Service />  

      <ChooseUs />
      
      <ReviewERating />

  </main>
</template>

<style lang="scss" scoped>
@import '../scss/general/variables';

main{
  min-height: 300px;
  // background-color: $backgroundSecondary;
}

</style>