<script>
export default {
    
}

</script>

<template>
    <section class="about-us">
        <img class="small-dog-bg" src="../../../../public/aboutUs-img/dog-logo.png" alt="">
        <div class="container">

            <div class="row">

                <div class="col left">
                    <img src="../../../../public/aboutUs-img/about.png" alt="">
                </div>

                <div class="col right">right</div>

            </div>
            
        </div>
        

    </section>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/variables';

.about-us{
    position: relative;
    background-color: $backgroundMain;

    .small-dog-bg{
        position: absolute;
        width: 100px;
    }
    .container{
        .row{
            .col.left{
                padding: 85px 25px;
                img{
                    width: 90%;
                }
            }
        }
    }
}

</style>