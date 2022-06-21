<template>
  <div class="main">
    <div class="header">
      <h1>These are my favorite games</h1>
    </div>

    <carousel :slides="slides" :interval="3000" controls indicators></carousel>
  </div>

  <div id="cat">
    <h1>Cat</h1>

    <div @mouseover="upHere = true" @mouseleave="upHere = false">
      <h2>Something Something</h2>
      <some-component v-show="upHere">
        <img src="http://placekitten.com/200/300" alt="cat1" />
        <img src="http://placekitten.com/200/301" alt="cat2" />
        <img src="http://placekitten.com/200/302" alt="cat3" />
        <img src="http://placekitten.com/200/303" alt="cat4" />
      </some-component>
    </div>

    <div class="btn">
      <button type="primary" @click="one()">Here is picture1.</button>
      <button type="primary" @click="two()">Here is picture2.</button>
    </div>
    <div>
      <img id="pic" style="width: 30%" :src="imgArr[0]" @mouseover="three()" />
    </div>
  </div>
</template>


<script>
import Carousel from "./components/carousel/CarouselWrapper.vue";

export default {
  name: "App",
  components: { Carousel },
  data: () => ({
    upHere: false,
    slides: [
      "https://static0.gamerantimages.com/wordpress/wp-content/uploads/2022/06/Elden_Ring_player_character_landscape.jpeg?q=50&fit=contain&w=960&h=500&dpr=1.5",
      "https://www.industriaanimacion.com/wp-content/uploads/2020/10/Cover-3.jpg",
      "https://i.redd.it/londmms0cwh71.jpg",
      "https://freegametips.com/wp-content/uploads/2019/11/Ori-and-the-Blind-Forest-Switch-Reviews-1024x576.jpg",
      "https://www.zmonster.me/assets/img/hollow_knight.jpg",
    ],

    url: "http://placekitten.com/200/300",
    url1: "http://placekitten.com/200/301",
    url2: "http://placekitten.com/200/302",
    url3: "http://placekitten.com/200/303",
    url4: "http://placekitten.com/200/304",
    url5: "http://placekitten.com/200/305",
    imgArr: [
      "http://placekitten.com/200/300",
      "http://placekitten.com/200/305",
    ],
    index: 0,
    i: 1,
  }),
  methods: {
    one() {
      var msg = document.getElementById("pic");
      msg.src = "http://placekitten.com/200/302";
    },
    two() {
      var msg = document.getElementById("pic");
      msg.src = "http://placekitten.com/200/305";
    },
    three() {
      var msg = document.getElementById("pic");
      msg.src = "http://placekitten.com/200/301";
    },
  },
};
</script>

<style scoped>
.main {
  background-image: url(https://64.media.tumblr.com/2747571410e13da622d918074e24c4ed/tumblr_obtkmwu74N1qa9gmgo1_1280.jpg);
}

.header h1 {
  text-align: center;
  position: relative;
  color: aqua;
}

.image {
  width: 100px;
  height: 100px;
  background-size: cover;
  cursor: pointer;
  margin: 5px;
  border-radius: 3px;
  border: 1px solid lightgray;
  object-fit: contain;
}
</style>
