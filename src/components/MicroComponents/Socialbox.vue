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
  
    <ul class="ul-social">
        <li>
            <a :class="name" :href="url">
                <i :class="logo"></i>
            </a>
        </li>
    </ul>

</template>

<style lang="scss" scoped>
@import '../../scss/general/general';
.ul-social{
    display: flex;
    align-items: center;
    list-style: none;
    height: 100%;
    margin: 0;

    .social-icons{
        display: inline-block;
        text-decoration: none;
        color: white;
        width: 25px;
        aspect-ratio: 1/1;
        border-radius: 5px;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 2px;
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