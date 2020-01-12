<template>
  <section class="page-container">
    <div class="section-heading">
      <h6>{{sectionHeading}}</h6>
    </div>
    <div class="magazine-grid">
      <!-- FIRST COLUMN BELOW -->
      <div class="first-column">

        <div class="highlight-text">
          <h4>{{highlightText}}</h4>
        </div>

        <div class="main-text">
          <p>{{mainText}}</p>
        </div>

        <specButton />
        <div class="magazine-image-container ipad-plus-only">
          <img class="magazine-image" :src="islandImage" alt="example image">
        </div>

         <!-- IPAD+ BUTTON BELOW-->
         <specButton class="ipad-plus-only"/>
         <!-- IPAD+ BUTTON ABOVE-->

      </div>
      <!-- FIRST COLUMN ABOVE -->

      <!-- SECOND COLUMN BELOW -->
      <div class="second-column">


        <!-- FEATURE GRID BELOW-->
        <div class="features-container">
          <feature v-for="(text, index) in featureText" :key="index" :text="text" :number="index"/>
        </div>
        <!-- FEATURE GRID ABOVE -->

        <!-- IPAD+ BUTTON BELOW-->
        <div class="magazine-image-container ipad-plus-only">
          <img class="magazine-image" :src="gallImage" alt="example image">
          <img class="magazine-image" :src="gallImage" alt="example image">
        </div>
        <!-- IPAD+ BUTTON ABOVE-->


        <!-- MOBILE CAROUSEL BELOW -->
        <div class="image-carousel mobile-only">
          <carousel />
        </div>
        <!-- MOBILE CAROUSEL ABOVE -->



        <specButton class="mobile-only"/>
      </div>
      <!-- SECOND COLUMN ABOVE -->
    </div>
  </section>
</template>

<script>
// COMPONENTS
import carousel from '~/components/carousel';
import specButton from '~/components/specButton';
import feature from '~/components/feature';

// IMAGES
import gallImage from '~/assets/images/gallimage.jpeg';
import islandImage from '~/assets/images/island.jpeg';
import palmImage from '~/assets/images/palm.jpeg';


export default {
  components: {
    carousel,
    specButton,
    feature,
  },
  data(){
    return{
      gallImage,
      islandImage,
      palmImage,
      sectionHeading: 'SECTION HEADING',
      highlightText: 'Highlight paragraph duis aute irure dolor in rephrehenderit in voluptate velit energy efficiency eu di fugiat.',
      mainText: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laundantium, totam rem aperiam, aeque ipsa quae ab illo inventore veritatis et quasi ventus vitae ventus consecutem terra lora magnum lorem aqua.',
      featureText:[
        'ICON LABEL LOREM IPSUM TERRA',
        'ICON LABEL LOREM IPSUM TERRA',
        'ICON LABEL LOREM IPSUM TERRA',
        'ICON LABEL LOREM IPSUM TERRA'
      ],
    }
  }
}
</script>

<style lang="scss">

.image-carousel{
  width: 100%;
  margin: 0 auto;
}
.features-container{
  display: flex;
  flex-direction: column;
  margin-bottom: 2em;
}

.ipad-plus-only{
  display: none;
}

.mobile-only.button-container{
  margin-left: 0.5em;
}

@media screen and (min-width: 768px){
  .mobile-only{
    display: none;
  }

  .button-container.ipad-plus-only{
    display: flex;
    margin-top: 3em;
  }

  .ipad-plus-only{
    display: block;
  }

  .magazine-grid{
    grid-template-columns: 1fr 1fr;
    grid-gap: 1.5em;
  }
  .features-container{
    margin-top: 0;
  }
  .magazine-image-container{
    display: grid;
    grid-gap: 1.5em;
  }

  // DO NOT HAVE ASSET, CREATED DUMMY HEIGHT TO REPLICATE RATIO (would not stretch image like this otherwise)
  .first-column{
    .magazine-image{
      height: 25em;
    }
  }
}

@media screen and (min-width: 1024px){
  .section-heading{
    margin-top: 1em;
  }
  .highlight-text{
    font-size: 1.2em;
  }
  .magazine-grid{
    width: 85%;
  }
  .features-container{
    flex-direction: row;
  }
  .first-column{
    .magazine-image{
      height: 26em;
    }
  }
}
@media screen and (min-width: 1920px){
  .page-container{
    margin: 4em 0 4em 5em;
  }
  .first-column{
    .magazine-image{
      height: 65em;
    }
  }
}
</style>
