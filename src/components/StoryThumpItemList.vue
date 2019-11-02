<template>
<div id="stories-list-wrapper">
  <div id="stories-list">
    <StoryThumpItem  v-for="member in members" :key="member.name"></StoryThumpItem>
  </div>
</div>
</template>
<script>
import StoryThumpItem from './StoryThumpItem'
export default {
  props:{
    members: {
      type: Array
    }
  },
  components:{
    StoryThumpItem
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
    grid-template-columns: repeat(1000, 55px);
    box-shadow: 0px 2px #EBEDEF;
}
@media screen and (min-width: 500px) {
  #stories-list{
    margin-top: 66px;
  }
}
</style>
