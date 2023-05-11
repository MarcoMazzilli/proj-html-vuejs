<script>
import Contacts from './MicroComponents/header/Contacts.vue';
import Menus from './MicroComponents/header/Menus.vue';

export default {
  
  components:{
    Contacts,
    Menus,

  }
  
}
</script>

<template>
  
  <!--HEADER TOP -->
  <Contacts />

  <!-- HEADER BOTTOM -->
  <Menus />

</template>

<style lang="scss" scoped>

</style>