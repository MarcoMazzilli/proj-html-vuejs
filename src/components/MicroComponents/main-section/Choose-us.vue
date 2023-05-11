<script>
import { chooseUs } from '../../../data/dbMainSection';
export default {
  data(){
    return{
      chooseUs
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
  <div class="container">
    <div class="row">

      <div class="col left">
        <img src="/public/assets/main-section/chooseUsSection-img/why.png" alt="">
      </div>
      <div class="col right">
        
        <!-- SECTION IMAGE -->
        <div class="section-name">
          <img src="../../../../public/assets/general/dog-icon.png" alt="dog icon">
          <h5>{{chooseUs.sectionName}}</h5>
        </div>
        
        <!-- SECTION NAME -->
        <div class="section-title">
          <h2>{{ chooseUs.sectionTitle }}</h2>
        </div>

        <!-- CARDS CONTAINER -->
        <div class="cards-container">
          
          <!-- CARD -->
          <div class="mm-card" v-for="(card,id) in chooseUs.card" :key="id">
            <!-- image -->
            <div class="img">
              <img :src="`/public/assets/main-section/chooseUsSection-img/${card.img}.png`" alt="Illustration">
            </div>
            <!-- description -->
            <div class="description">
              <h4>{{ card.title }}</h4>
              <p>{{ card.description }}</p>
            </div>

          </div>

        </div>

      </div>

    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '../../../scss/general/variables';
.container{
  max-width: 100% !important;
  .row{
    margin: 0;

    .col.left{
      max-width: 50%;
      padding: 0;
    }

    .col.right{
      padding: 70px 50px;

      .section-name{
        display: flex;
        align-items: center;
        gap: 10px;
        margin-bottom: 20px;

        img{
          width: 70px;
        }
        h5{
          color: $brandSecondary ;
        }
      }
      .section-title{
        margin-bottom: 40px;
        h2{
          font-size: 2.7rem;
          font-weight: 600;
        }
      }
      .cards-container{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        .mm-card{
          display: flex;

          &:nth-child(2){
            width: 80%;
          }
          &:nth-child(3){
            width: 55%;
          }
          img{
            margin-right: 30px;
            width: 170px;
          }
          .description{
            h4{
              font-weight: 600;
              margin-bottom: 10px;
            }
            p{
              font-size: 1.2rem;
            }
          }
        }
      }
    }
  }
}

</style>