
<script>
import { aboutUs } from '../../../data/dbMainSection';

export default {
    data(){
        return{
            aboutUs,

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
    <section class="about-us">
        <img class="small-dog-bg" src="/assets/general/dog-logo.png" alt="Dog image">
        <div class="container">

            <div class="row">
                <!-- IMGAGE LEFT -->
                <div class="col left">
                    <img src="/assets/main-section/aboutUs-img/about.png" alt="Dog image">
                </div>
                <!-- INFO RIGHT -->
                <div class="col right">
                    <div class="info">
                        <!-- SECTION NAME  -->
                        <div class="section-name">
                            <img :src="`/public/assets/general/${aboutUs.img}.png`" :alt="aboutUs.img">
                            <h5>{{aboutUs.sectionName}}</h5>
                        </div>
                        <!-- SECTION DESCRIPTION -->
                        <div class="section-description">

                            <h2>{{ aboutUs.sectionTitle }}</h2>
                            <p>{{ aboutUs.sectionDescriptionTop }}</p>
                            <p>{{ aboutUs.sectionDescriptionBottom }}</p>

                        </div>

                    </div>
                </div>

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
        width: 250px;
        right: 0;
        top: 85px;
    }
    .container{
        .row{
            padding: 85px 15px;
            .col.left{
                img{
                    width: 90%;
                }
            }
            .col.right{
                display: flex;
                align-items: center;
                .info{
                    margin-left: 15px;
                    padding:  35px 0px;
                    height: 80%;
                    .section-name{
                        display: flex;
                        align-items: center;
                        gap: 15px;
                        margin-bottom: 30px;
                        img{
                            width: 40px;
                        }
                        h5{
                            color: $brandSecondary;
                            font-size: 1rem;
                        }
                    }
                    .section-description{
                        h2{
                            font-size: 2.5rem;
                            font-weight: 800;
                            margin-bottom: 25px;
                        }
                        p{
                            font-size: 1.1rem;
                        }
                    }
                }
            }
        }
    }
}

</style>