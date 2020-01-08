<template lang='pug'>
<div id="WasIstIOTA">
    <div class="eg-slideshow">
      <slide>
          <h1>Was ist IOTA?</h1>
          <h4>Die Grundlagen einfach erklärt!</h4>
      </slide>
      <slide enter="bounceInRight" leave="fadeOut">
          <h3>Hey modify me !</h3>
          <p>Come on modify me ! If you are running the development server, you will see the changes take effect immediately
          </p>
      </slide>
      <slide enter="fadeIn">
          <h3>Want cool effects?</h3>
          <p>Code your own, or try stealing for the other slideshows !</p>
      </slide>
    </div>
</div>
</template>

<script>
import eagle from 'eagle.js'
export default {
  mixins: [ eagle.slideshow ],
  infos: {
    // These infos appear on the home page, below the slideshow's thumbnail
    title: 'Was ist IOTA?',
    description: 'Die Grundlagen einfach erklärt.',
    path: 'was-ist-iota'
  }
}
</script>

<style lang='scss'>
@import url(https://fonts.googleapis.com/css?family=Raleway);
#MyFirstSlideshow{
  .eg-slideshow{
    font-family: 'Raleway';
    background-color: #eef;
    .eg-slide{
      .eg-slide-content{
        width: 25em;
        max-width: 80%;
        margin: 0 auto;
      }
    }
  }
  .eg-slide-content{
    width: 25em;
    max-width: 80%;
    margin: 0 auto;
  }
}
</style>
