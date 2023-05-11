<script>
import {service} from '../../../data/dbMainSection'
export default {
    data(){
        return{
            service
        }
    },
    methods:{
        getImage(img){
            return new URL(img, import.meta.url).href;
        }
}
    
}

</script>

<template>
<section class="service">

    <img class="dog-left" src="/public/assets/general/dog-left.png" alt="">
    <img class="dog-right" src="/assets/general/dog-logo.png" alt="">

    <div class="container">

        <div class="row top">
            <!-- SECTION NAME -->
            <div class="col top">
                <h5>{{ service.sectionName }}</h5>
                <h2>{{ service.sectionTitle }}</h2>
            </div>

        </div>
        <!-- CARDS CONTAINER -->
        <div class="row bottom">

            <div class="col bottom"  v-for="(card,id) in service.card" :key="id" >

                <div class="mm-card">
                    <img :src="`/assets/main-section/serviceSection-img/${card.img}.png`" alt="dog icon">
                    <h6>{{ card.title }}</h6>
                    <p>{{ card.description }}</p>
                    <div class="mm-button">
                        <i class="fa-solid fa-angle-right"></i>
                    </div>

                </div>

            </div>

        </div>

    </div>

</section>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/variables';

.service{
    height: 585px;
    background-color: $backgroundSecondary;
    position: relative;

    .dog-left{
        width: 180px;
        position: absolute;
        top: 60px;
    }
    
    .dog-right{
        width: 250px;
        position: absolute;
        right: 0;
        top: 60px;
    }

    .container{
        height: 100%;
        padding: 0;
        .row{
            display: flex;
            flex-direction: column;
            max-width: 100%;
            margin: 0;
            &.top{
                height: 35%;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            &.bottom{
                height: 65%;
            }

            .col.top{
                text-align: center;
                width: 40%;
                padding-top: 35px;
                
                h5{
                   color: $brandSecondary;
                   font-size: 1.2rem;
                   margin: 25px;
                }
                h2{
                    font-weight: 600;
                }
            }
            // CONTAINER CARDS //
            .col.bottom{
                display: flex;
                padding: 20px;
                width: calc(100% / 5);
                
                // MM-CARD //
                .mm-card{
                    height: 305px;
                    width: 190px;
                    border-radius: 100px;
                    background-color: $brandMain;
                    text-align: center;
                    padding: 20px;
                    color: white;

                    &:hover{
                        background-color: $brandSecondary;
                    }

                    img{
                        width: 45%;
                        margin-bottom: 20px;
                    }
                    h6{
                        font-size: 1.1rem;
                        font-weight: 600;
                    }
                    p{
                        margin-bottom: 40px;
                    }
                    .mm-button{
                        margin: 0 auto;
                        text-align: center;
                        width: 50px;
                        height: 50px;
                        border-radius: 100px;
                        background-color: $serviceBtn;
                        color: black;
                        font-size: 2.2rem;
                    }
                }
            }
        }
    }
}


</style>