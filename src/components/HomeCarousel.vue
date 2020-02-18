<template>
  <q-page style="min-height: 300px;">
    <q-responsive
      :ratio="16/9"
      style="width: 500px; max-width: 100%;"
    >
      <q-carousel
        :autoplay="autoplay"
        arrows
        animated
        swipeable
        ref="carousel"
        infinite
        v-model="slide"
        background-color="black"
      >
        <q-carousel-slide
          name="first"
          img-src="https://d2zdpiztbgorvt.cloudfront.net/us/images/77223/inspiration_154750217177.jpeg?size=1170x1170"
          alt="Photo by mark glancy from Pexels"
        >
          <div class="absolute-center custom-caption">
            <div class="text-h3">Text 1</div>
            <div class="text-subtitle1">
              Some text 1
            </div>
          </div>
        </q-carousel-slide>
        <q-carousel-slide
          name="second"
          img-src="https://d2zdpiztbgorvt.cloudfront.net/us/images/77223/inspiration_153494496566.jpeg?size=1170x1170"
        >
          <div class="absolute-center custom-caption">
            <div class="text-h3">Text 2</div>
            <div class="text-subtitle1">Some text 2</div>
          </div>
        </q-carousel-slide>
        <q-carousel-slide
          name="third"
          img-src="https://d2zdpiztbgorvt.cloudfront.net/us/images/77223/inspiration_153265240204.jpeg?size=1170x1170"
        >
          <div class="absolute-center custom-caption">
            <div class="text-h3">Text 3</div>
            <div class="text-subtitle1">
              Some text 3
            </div>
          </div>
        </q-carousel-slide>
        <template v-slot:control>
          <q-carousel-control
            position="top-right"
            :offset="[18, 18]"
            class="text-white"
            style="background: rgba(0, 0, 0, .3); padding: 4px 8px 4px 0; border-radius: 4px"
          >
            <q-toggle
              dense
              dark
              color="yellow"
              v-model="autoplay"
              label="Auto Play"
            />
          </q-carousel-control>
        </template>
      </q-carousel>
    </q-responsive>
  </q-page>
</template>

<script>
import { openURL } from "quasar";

export default {
  name: "HomeCarousel",
  data () {
    return {
      slide: "first",
      autoplay: false
    };
  }
};
</script>

<style scoped>
.carousel-light {
  background: linear-gradient(270deg, red, orange);
}
.carousel-dark {
  background: linear-gradient(270deg, purple, teal);
}

.custom-caption {
  text-align: center;
  padding: 30px;
  color: white;
  background-color: rgba(0, 0, 0, 0.4);
}

.my-card {
  width: 100%;
  max-width: 10000px;
}

@media only screen and (max-width: 731px) {
  .button-1 {
    margin-top: 1em;
  }
  .button-2 {
    margin-top: 1em;
  }
}

@media only screen and (max-width: 767px) {
  .button-1 {
    transform: scale(0.75);
  }
  .button-2 {
    transform: scale(0.75);
  }
}

@media only screen and (min-width: 768px) {
  .text-h2 {
    font-size: 7em;
    line-height: 1em;
    padding-bottom: 0.2em;
  }
  .custom-caption {
    text-align: center;
    padding: 30px;
    padding-top: 3em;
    width: Auto;
    color: white;
    background-color: rgba(0, 0, 0, 0.4);
  }
  .text-subtitle1 {
    font-size: 2em;
    padding-bottom: 1em;
  }
  .button-1 {
    margin-right: 3em;
  }
  .button-2 {
    margin-left: 3em;
  }
}

.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
</style>
