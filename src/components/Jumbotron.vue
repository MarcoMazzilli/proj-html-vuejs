<script>
export default {
  name: 'Jumbotron'
  
}
</script>

<template>
  <div class="wrapper">

    <div class="container">
      <div class="hero-description">

        <div class="title">
          <h1> Welcome to  <span>DogMilo</span> Pets </h1>
        </div>

        <div class="description">
          <span> Lorem Ipsum is simply dummy text of the printing and typesetting industry. </span>
        </div>

        <div class="cta-buttons">
          <span>Get Started</span>
          <a href="#"><img src="/jumbotron-img/play.png" alt="Play png"></a>
        </div>

      </div>
      
      
    </div>

  </div>
</template>

<style lang="scss" scoped>
@import "../scss/general/variables";

.wrapper{
  height: 575px;
  background-image: url(/jumbotron-img/b.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  position: relative;

  .container{
    height: 100%;
    display: flex;
    align-items: center;

    .hero-description{
    
      width: 500px;
      height: 300px;

      .title{
        width: 80%;
        margin-bottom: 20px;
        h1{
          color: white;
          font-size: 3rem;
          font-weight: 900;
          span{
            font-weight: 400;
          }
        }
      }
      .description{
        width: 85%;
        margin-bottom: 35px;
        span{
          color: white;
          font-size: 1.2rem;
        }
      }
      .cta-buttons{
        display: flex;
        align-items: center;
        gap: 10px;      

        span:first-child{
          font-size: 1.5rem;
          font-weight: 600;
          color: white;
          background-color: $brandMain;
          padding: 10px 33px;
          border-radius: 50px;
          cursor: pointer;
          transition: .3s;

          &:hover{
            background-color: $hoverBtn;
          }
        }

        a img{
          height: 50px;
          padding: 10px;
          border-radius: 10px;
          background-color: rgb(112, 208, 247);
          cursor: pointer;

          
        }
      }
    }
  }
}



</style>