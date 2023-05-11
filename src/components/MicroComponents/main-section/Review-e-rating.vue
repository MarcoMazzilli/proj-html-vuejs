<script>
import { reviewRating } from '../../../data/dbMainSection';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation } from 'swiper';
import 'swiper/css';
import 'swiper/css/navigation';

export default {
    data(){
      return{
        reviewRating
      }
    },
    methods:{
      getImage(img){
        return new URL(img, import.meta.url).href;
      }
    },
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      return {
        modules: [Navigation],
      };
    },
}

</script>

<template>
  <section class="review-rating">
    <div class="container">
      <div class="row">

        <div class="col col-4 left">

          <div class="section-name">
            <img src="/public/assets/general/dog-icon.png" alt="dog icon">
            <h5>Review & Rating</h5>
          </div>

          <div class="section-description">
            <h2>{{ reviewRating.sectionTitle}}</h2>
            <p>{{ reviewRating.sectionDescription }}</p>
          </div>

          <div class="stars">
            <i  
            v-for="star in reviewRating.sectionRating" 
            :key="star" 
            class="fa-solid fa-star"></i>
          </div>



        </div>

        <div class="col col-8 right">
          <swiper :navigation="true" :modules="modules" class="mySwiper review" :slides-per-view="2" :loop="Infinity">

            <swiper-slide  v-for="(card,id) in reviewRating.cards" :key="id">

              <div class="mm-card">
                
                <div class="stars">
                  <i v-for="rate in card.rating" :key="rate" class="fa-solid fa-star"></i>
                </div>
                
                <div class="card-description">
                  <h6>{{ card.title }}</h6>
                  <p>{{ card.description }}</p>
                </div>
                
                <div class="card-user-information">
                  <div class="img-container">
                    <img :src="`/public/assets/main-section/review-rating-img/${card.userAvatar}.png`" alt="Avatar">
                  </div>
                  
                  <div class="description-container">
                    <span class="name">{{ card.userName }}</span>
                    <span class="job">{{ card.userJob }}</span>
                  </div>
                
                </div>
              
              </div>
            
            </swiper-slide>
          </swiper>
        </div>

      </div>
    </div>

  </section>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/variables';

.stars{
  i{
    font-size: .9rem;
    color: $ratingStars;
  }
}

.review-rating{
  min-height: 640px;
  padding-top: 90px;

  .container{
    .row{
      margin: 0;

      .col.left{

        .section-name{
          display: flex;
          gap: 15px;
          align-items: center;
          margin-bottom: 15px;

          img{
            width: 20px;
          }
          h5{
            font-size: 1.1rem;
            font-weight: 500;
            color: $brandSecondary ;
          }
        }
        .section-description{
          h2{
            font-size: 1.9rem;
            font-weight: 600;
            margin-bottom: 30px;
          }
          p{
            margin-bottom: 30px;
          }
        }

      }
      .col.right{
        display: flex;
        
        .mm-card{
          width: 350px;
          height: 300px;
          background-color: $backgroundSecondary;
          margin: 0 15px;
          padding: 15px;

          .stars{
            margin-bottom: 15px;
          }

          .card-description{
            margin-bottom: 30px;
            h6{
              font-size: 1.4rem;
              font-weight: 600;
              margin-bottom: 15px;
            }
            p{
              font-size: 1.1rem;
            }
          }

          .card-user-information{
            display: flex;
            align-items: center;
            gap: 20px;
            height: 65px;

            img{
              width: 55px;
              border-radius: 50%;
            }
            .description-container{
              height: 100%;
              display: flex; 
              flex-direction: column;
              justify-content: space-around;
              padding: 5px 0;

              span:first-child{
                font-size: 1.1rem;
                font-weight: 600;
              }
              span:last-child{
                font-size: .8rem;
              }
            }
          }
        }
      }
    }
  }
}

</style>