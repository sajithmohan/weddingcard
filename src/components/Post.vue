<template>
<div>
  <div class="post-head">
    <div class="dp-pic">
      <img src="https://scontent-frx5-1.cdninstagram.com/vp/3b7b7aae3e544938209e85c923cd9b7a/5E2BFF4B/t51.2885-19/s150x150/53506516_631844110571928_1075002637419544576_n.jpg?_nc_ht=scontent-frx5-1.cdninstagram.com" width="30px" height="30px"/>
    </div>
    <div class="post-head-text">
      <h5> Sajith </h5>
      <h7> kannur </h7>
    </div>
  </div>
  <img width="100%" src="https://scontent-frx5-1.cdninstagram.com/vp/1592de1e585a51eeb09e8cc1d2266635/5E2B3A44/t51.2885-15/e35/72326783_168797390940191_7053864174228740588_n.jpg?_nc_ht=scontent-frx5-1.cdninstagram.com&_nc_cat=111"/>
  <div class="post-footer-icons">
    <i class="material-icons"> favorite_border </i>
    <i class="material-icons"> chat_bubble_outline </i>
    <i class="material-icons-outlined rotated">send</i>
  </div>
  <div class="post-likes">
    5,499 likes
  </div>
  <div class="post-description">
      <b>Sajith</b>&nbsp;&nbsp;&nbsp;-
      Join our Tribe @travelstribe
      -
      Photo by @marcobauer1 | #travelstribe
      Hashtags:
      #climbing #jurassicpark #sardinia #adventure #adventuretime #traveller #traveler #travellers #travelers #travel_drops #traveldeeper
  </div>
</div>
</template>
<script>
export default {

}
</script>
<style>
.post-head{
  height: 50px;
  display:grid;
  grid-template-columns: 0fr 1fr;
}
.dp-pic{
  width: 50px;
}
.dp-pic img {
  margin: 10px;
  border-radius: 15px;
}
.post-head-text{
  line-height: 15px;
  padding-top: 10px;
}
.post-head-text h5, h7 {
  margin: 0px
}
.post-footer-icons i{
  margin-left: 10px;
  margin-right: 10px;
  line-height: 24px;
  margin-top: 12px;
}
.post-likes{
  padding-left: 10px;
  margin-top: 10px;
  font-weight:1000;
  font-size: 12px;
}
.post-description {
  font-size: 12px;
  padding: 10px;
}
</style>
