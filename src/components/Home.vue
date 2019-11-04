<template>
  <div>
    <div id="mainContainer" v-if="loaded">
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
    <div id="loading-screen" v-if="!loaded">
      <div class="loader"></div>
    </div>
  </div>

</template>
<script>

import InstHead from './InstaHead'
import Post from './Post'
import Footer from './Footer'
import StoryThumpItemList from './StoryThumpItemList'
import StoriesOfPerson from './StoriesOfPerson'
import  axios from 'axios'

export default {
  data(){
    return {
      loaded: false,
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
  async created(){
    const urlPromises = []
    this.members.forEach((member, mIndx) => {
      member.stories.forEach((story, sIndex) => {
        urlPromises.push(this.getBolob(story.url, {mIndx, sIndex}))
      })
    });
    const resultData = await Promise.all(urlPromises)
    resultData.forEach(d => {
      // debugger
      this.members[d.mIndx].stories[d.sIndex].blob = d.blob
    })
    this.loaded = true
    setTimeout(() => this.activeStoryPerson = this.members[0], 5000)
  },
  computed: {
    selectedMembers(){
      return this.members
    }
  },
  methods:{
    async getBolob(url, data){
      const response = await axios.get(url, {responseType: 'arraybuffer'})
      data.blob = new Buffer(response.data, 'binary').toString('base64')
      return data
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
#loading-screen {
  background-image: url("/assets/whatsapp-status.jpeg");
  background-size:cover;
  height: 100vh;
}
.loader {
  border: 16px solid #f3f3f3; /* Light grey */
  border-top: 16px solid #555; /* Blue */
  border-radius: 50%;
  width: 120px;
  height: 120px;
  animation: spin 2s linear infinite;
  margin-left: auto;
  margin-right: auto;
  position: relative;
  top: 30vh;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
