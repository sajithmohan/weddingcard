<template>
  <div id="mainContainer">
    <div id="story-main-wrapper" v-if="activeStoryPerson != null">
      <StoriesOfPerson v-if="activeStoryPerson" :person="activeStoryPerson"> </StoriesOfPerson>
    </div>
    <div id="home-main-wrapper" v-if="activeStoryPerson === null">
      <InstHead></InstHead>
      <StoryThumpItemList :members="members"></StoryThumpItemList>
      <div class="post-content">
        <Post v-for="index in 10" :key="index"></Post>
      </div>
      <Footer></Footer>
    </div>
  </div>
</template>
<script>

import InstHead from './InstaHead'
import Post from './Post'
import Footer from './Footer'
import StoryThumpItemList from './StoryThumpItemList'
import StoriesOfPerson from './StoriesOfPerson'
export default {
  data(){
    return {
      activeStoryPerson: null,
      members: [{
        name: "sajith",
        dp: "https://scontent-frx5-1.cdninstagram.com/vp/3b7b7aae3e544938209e85c923cd9b7a/5E2BFF4B/t51.2885-19/s150x150/53506516_631844110571928_1075002637419544576_n.jpg?_nc_ht=scontent-frx5-1.cdninstagram.com",
        stories:[

          {
            id: 5,
            url: "/assets/status/vid100.mp4",
            type: "video",
          },
          {
            id: 6,
            url: "/assets/status/vid101.mp4",
            type: "video",
          },
          {
            id: 7,
            url: "/assets/status/vid102.mp4",
            type: "video",
          },
          {
            id: 1,
            url: "/assets/whatsapp-status.jpeg",
            type: "image",
          },
          {
            id: 2,
            url: "/assets/story1.jpg",
            type: "image"
          },{
            id: 3,
            url: "/assets/whatsapp-status.jpeg",
            type: "image",
          },
          {
            id: 4,
            url: "/assets/story1.jpg",
            type: "image"
          }
        ],
        posts: [

        ]
      }]
    }
  },
  created(){
    setTimeout(() => this.activeStoryPerson = this.members[0], 500)
  },
  computed: {
    selectedMembers(){
      return this.members
    }
  },
  components:{
    InstHead,
    Post,
    Footer,
    StoryThumpItemList,
    StoriesOfPerson
  }
}
</script>
<style>
  html{
    height: 100%;
  }
  body{
    background: black;
    height: 100%;
    font-family: 'Raleway', sans-serif;
  }
  #mainContainer{
    max-width: 500px;
    margin: auto;
    background: white;
    overflow: hidden;
  }
  #app{
    height: 100%;
  }
::-webkit-scrollbar {
    width: 0px;  /* Remove scrollbar space */
    background: transparent;  /* Optional: just make scrollbar invisible */
}
#story-main-wrapper {
  position:static;
  top: 0px;
  left: 0px;
  /* background: red; */
  width: 100%;
  height: 100vh;
}
</style>
