<script>
export default {
    props:{
         name: String,
         url: String,
         logo: String,
    }
    
}
</script>

<template>
  
    <!-- <ul class="ul-social"> -->
        <li class="li-social">
            <a class="social-icons" :class="name" :href="url">
                <i :class="logo"></i>
            </a>
        </li>
    <!-- </ul> -->

</template>

<style lang="scss" scoped>
@import '../../../scss/general/general';
.li-social{
    list-style: none;

    .social-icons{
        display: flex;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        width: 25px;
        aspect-ratio: 1/1;
        margin: 0 2px;
        border-radius: 5px;
        color: white;
        &.facebook{
            background-color: rgb(48, 63, 191);
        }
        &.pinterest{
            background-color: rgb(190, 44, 76);
        }
        &.twitter{
            background-color: rgb(124, 207, 211);
        }
        &.linkedin{
            background-color: rgb(6, 99, 207);
        }
        &.instagram{
            background-color: rgb(167, 33, 179);
        }
    }    
}


</style>