<template>
  <div class="story">

    <div  class="story-timer-wrapper">
      <div class="story-time-main" v-for="story in person.stories" v-bind:key="story.id">
        <div class="story-time-inner" v-bind:class="{'story-time-inner-active': currentStory != null && story.id === currentStory.id}">
        </div>
      </div>
    </div>
    <div class="story-content" v-if="currentStory">
      <img v-if="currentStory.type === 'image'" :src="currentStory.url" width="100%" height="100%"/>
      <div v-for="story in person.stories" v-bind:key="story.id" >
      <video v-if="currentStory.type === 'video' && currentStory.id ===story.id"  width="100%" height="100%" autoplay controls >
        <source :src="story.url" type="video/mp4">
      </video>
      </div>

    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      currentStory: null,
      storyDisplayTime: 5000
    }
  },
  props: {
    person:{
      type: Object
    }
  },
  created(){
    this.person.stories.forEach((story, index) => {
      setTimeout(() => this.currentStory = story,  index * this.storyDisplayTime)
    });
  },
  computed: {
    source(){
      return `<source src="${this.currentStory.url}" type="video/mp4">`
    }
  },
}
</script>
<style>
.story-timer-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(5px, 1fr));
  grid-column-gap: 2px;
  height: 2px;
  padding-left: 5px;
  padding-right: 5px;
  position: relative;
  top: 10px;
  z-index: 10;
}
.story-time-main{
  width: 100%;
  height: 2px;
  background: #c2c2c2;
  border-radius: 2px;
  opacity: 0.5;
}
.story-time-inner {
  position: relative;
  top: 0px;
  left: 0px;
  width: 0%;
  height: 2px;
  background: #ffffff;

}
.story-time-inner-active {
  width: 100%;
  transition: width 5s;
}


.story-content{
  position: relative;
  top: -10px;
  left: 0px;
}
</style>
