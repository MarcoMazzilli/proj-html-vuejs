<script>
import dbContacts from '../data/dbContacts'
import Socialbox from './MicroComponents/generalMicro/Socialbox.vue'
import navLinks from '../data/dbFooter'
export default {
  components: { 
    Socialbox 
  },
  data(){
    return{
      dbContacts,
      navLinks,
      isActive : false,

    }
  }
  
}
</script>

<template>
<section class="footer">

  <div class="container newsletter">
    <div class="row">

      <div class="col left ">
        <img src="/public/assets/footer-img/news.png" alt="Dogs Image">
      </div>

      <div class="col right">

        <h4>Subscribe to Our Newsletter</h4>
        <!-- questo ha il focus!!! -->
        <div class="input-container" :class="isActive ? 'active' : null">

          <input type="text" placeholder="Your Email Here" @click="isActive = !isActive">
          <div class="square"></div>

        </div>

      </div>
    </div>

  </div>

<div class="container link">
  <div class="row">

    <div  id="get-in-touch" class="col col-3">
      <h3>Get in Touch</h3>
      <p>Have a Question for us? <br> we'll answer your problem here </p>
      <ul class="ul-social">
        <Socialbox v-for="social in dbContacts.social" :key="social"
          :name="social.name"
          :url="social.url"
          :logo="social.logo"
        />
      </ul>
    </div> 
<!-- QUESTO VA IN LOOP -->
    <div class="col" v-for="(section,i) in navLinks" :key="i">
      <h3>{{ section.title }}</h3>
      <ul>
         <li v-for="(link,id) in section.links" :key="id">
          <a href="#">{{ link }}</a></li>
      </ul>
    </div>

    <div id="contact-me" class="col col-3">

      <h3>Contact Me</h3>


      <div class="info">
        <i class="fa-solid fa-location-arrow"></i>
        <span>{{ dbContacts.address }}</span>
      </div>
      <div class="info">
        <i class="fa-solid fa-phone"></i>
        <span>{{ dbContacts.phoneNumber }}</span>
      </div>
      <div class="info">
        <i class="fa-solid fa-envelope"></i>
        <span>{{ dbContacts.mail }}</span>
      </div>

    </div>

  </div>


</div>

</section>
<section class="copiright">

  <span>Copyright 2022 by AttdogMilo.com</span>

</section>


</template>

<style lang="scss" scoped>
@import '../scss/general/variables';

.footer{
  background-color: #000000;
  position: relative;
  padding-top: 150px;
  padding-bottom: 40px;

  //CONTAINER TOP //
  .container.newsletter{
    position: absolute;
    width: 48%;
    height: 200px;
    top: 0;
    left: 50%;
    transform: translate(-50% , -50%);
    border-radius: 10px ;
    background-color: $brandMain;

    .row{
      height: 100%;
      .col.left{
        position: relative;
        height: 100%;
        img{
          width: 75%;
          position: absolute;
          bottom: 0;
          left: 50%;
          transform: translateX(-50%);
        }
      }

      .col.right{
        display: flex;
        flex-direction: column;
        justify-content: center;
        

        h4{
          color: white;
          font-weight: 600;
          font-size: 1.6rem;
          margin-bottom: 20px;
        }
        .input-container{
          width: 95%;
          display: flex;
          padding: 3px;
          outline: 2px solid rgba(0,0,0,0);
          background-color: white;

          &:hover{
            outline: 2px solid rgb(0, 122, 255);
            outline-offset: -3px;
          }
          &.active{
            outline: 2px solid rgb(0, 122, 255);
            outline-offset: -3px;
          }

          input{
            width: calc(100% - 60px);
            border: none;
            background-color: none;
            outline: none;
            margin: 10px;
          }

          .square{
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: $brandMain;
            width: 50px;
            aspect-ratio: 1/1;
            

            &::before{
              content: '\0040';
              color: white;
              font-size: 2rem;
            }
          }
        }
      }
    }
  }
  // CONTAINER BOTTOM //
  .container.link{
    height: 200px;
    color: $txtColor;

    ul{
      padding: 0; 
      li{
        list-style: none;
        margin-bottom: 8px;
        a{
          text-decoration: none;
          color: $txtColor;

          &:hover{
            color: white;
          }
        }
      }
    }

    h3{
      color: $brandMain;
      font-size: 1.4rem;
      font-weight: 600;
      margin-bottom: 20px;
    }
    p{
      margin-bottom: 25px;
    }
    .row{
      margin: 0;
    }

    #get-in-touch{
      .ul-social{
          display: flex;
          padding: 0;
        }
    }

    #contact-me{
      .info{
        display: flex;
        align-items: center;
        gap: 10px;
        margin-bottom: 25px;
        i{
          color: $brandMain;
        }
      }
    }
  }
}
.copiright{
  padding: 25px;
  text-align: center;
  background-color: black;
  border-top: 1px solid rgb(41, 41, 41);
  color: white;
}



</style>