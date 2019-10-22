<template>
  <div id="mainContainer">
    <InstHead></InstHead>
    <StoriesList></StoriesList>
    <div class="post-content">
      <Post v-for="index in 10" :key="index"></Post>
    </div>
    <Footer></Footer>
  </div>
</template>
<script>

import InstHead from './InstaHead'
import Post from './Post'
import Footer from './Footer'
import StoriesList from './StoriesList'

export default {
  components:{
    InstHead,
    Post,
    Footer,
    StoriesList
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
</style>
