<template>
  <div class="frontpage">
    <div class="content">
      <h1>
        <span class="logo"></span>
        <span>Workshop</span>
      </h1>
      <h2>Lerne die Grundlagen von IOTA und wie man mit dem Tangle arbeitet.</h2>
      <iframe
        class="github-star"
        src="https://ghbtns.com/github-btn.html?user=einfachiota&amp;repo=einfachIOTA.de&amp;type=star&amp;count=true&amp;size=large"
        frameborder="0"
        scrolling="0"
        width="160px"
        height="30px"
      ></iframe>
      <h3>IOTA Grundlagen</h3>
      <div class="thumbnails">
        <div class="box-card" v-for="(introduction, index) in introductions" :key="index">
          <router-link :to="introduction.infos.path" @click.native="click">
            <div class="embedded-slideshow-container">
              <component
                :is="introduction"
                :embedded="true"
                :keyboardNavigation="false"
                :mouseNavigation="false"
              ></component>
            </div>
          </router-link>
          <div class="caption">
            <h3>{{introduction.infos.title}}</h3>
            <p class="thumbnail-description">{{introduction.infos.description}}</p>
          </div>
        </div>
      </div>
      <h3>Javascript IOTA Workshop</h3>
      <p>
        Der Javascript IOTA Workshop hilft Entwicklern, und jene, die es werden wollen, bei dem Einstieg in den Tangle.
      </p>
      <p>Mit einer Schritt für Schritt anleitung und viele nützliche Tipps ist dieser Workshop der Perfekt <Startpunkt class="s"></Startpunkt></p>
      <div class="thumbnails">
        <div class="box-card" v-for="(slideshow, index) in slideshows" :key="index">
          <router-link :to="slideshow.infos.path" @click.native="click">
            <div class="embedded-slideshow-container">
              <component
                :is="slideshow"
                :embedded="true"
                :keyboardNavigation="false"
                :mouseNavigation="false"
              ></component>
            </div>
          </router-link>
          <div class="caption">
            <h3>{{slideshow.infos.title}}</h3>
            <p class="thumbnail-description">{{slideshow.infos.description}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import slideshows from 'slideshows/slideshows'

export default {
  data: function () {
    return {
      introductions: slideshows.introduction,
      slideshows: slideshows.list
    }
  },
  mounted: function () {
    console.log(this.slideshows)
    document.currentSlide = {}
  },
  methods: {
    click: function (evt) {
      evt.stopPropagation()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
@import "node_modules/eagle.js/src/themes/frontpage/frontpage";

.logo {
  display: inline-block;
  width: 100px;
  height: 100px;
  margin-right: 0.1em;
  background-image: url(./logo.svg);
  background-size: contain;
  background-position: center bottom;
  background-repeat: no-repeat;
}

.github-star {
  display: block;
  margin: 0 auto;
  margin-top: -10px;
}
</style>
