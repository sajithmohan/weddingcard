<template>
<div id="stories-list-wrapper">
  <div id="stories-list">
    <StoryItem  v-for="index in 10" :key="index"></StoryItem>
  </div>
</div>
</template>
<script>
import StoryItem from './StoryItem'
export default {
  components:{
    StoryItem
  }
}
</script>
<style>
#stories-list{
    margin-top: 16vw;
    height: 72px;
    display: grid;
    grid-gap: 20px;
    padding: 5px 20px;
    overflow-x: scroll;
    grid-template-columns: repeat(6, 60px);
    box-shadow: 0px 2px #EBEDEF;
}
@media screen and (min-width: 500px) {
  #stories-list{
    margin-top: 66px;
  }
}
</style>
