<template>
  <div class="feature">
    <h3 class="feature-number">0{{number+1}}</h3>
    <img :src="square" alt="">
    <p>{{text}}</p>
  </div>
</template>

<script>
import square from '~/assets/icons/square.svg';

export default {
  props:['text', 'number'],
  components:{
  },
  data(){
    return{
      square
    }
  }
}
</script>

<style lang="scss">
  .feature{
    display: flex;
    align-items: center;
    text-align: center;
    font-family: 'Roboto Slab';
    p{
      font-size: 12px;
      margin: 0;
      margin-left: 20px;
      letter-spacing: 0.5px;
      color: #27198C;
    }
    img{
      width: 40px;
    }
    margin-top: 1em;
  }
  .feature-number{
    color: #E5E5E5;
    margin-left: -1.5em;
    font-family: 'Muli';
    font-weight: 900;
    margin-bottom: 3px;
    display: none;
  }

  @media screen and (min-width: 768px){
    .feature:first-child{
      margin-top: 0.5em;
    }
  }
  @media screen and (min-width: 1024px){
    .feature-number{
      display: block;
    }
    .feature:first-child, .feature{
      margin-top: 0.5em;
    }
    .feature{
      flex-direction: column;
      p{
        margin-top: 1em;
        font-size: 9px;
      }
      img{
        width: 60px;
      }
    }
  }
</style>