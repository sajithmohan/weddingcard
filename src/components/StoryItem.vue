<template>
<div class="story-border">
  <img class="story-dp-pic" src="https://scontent-frx5-1.cdninstagram.com/vp/3b7b7aae3e544938209e85c923cd9b7a/5E2BFF4B/t51.2885-19/s150x150/53506516_631844110571928_1075002637419544576_n.jpg?_nc_ht=scontent-frx5-1.cdninstagram.com" />
</div>
</template>
<script>
export default {

}
</script>
<style>
.story-border {
  width: 60px;
  height: 60px;
  border-radius: 30px;
  background-image: linear-gradient(-120deg, red, yellow);
  padding: calc(var(--gutter) / 2 * 1.5);
  display: flex;
  flex-direction: column
}

.story-dp-pic {
    width: 54px;
    height: 54px;
    border-radius: 27px;
    margin-top: 3px;
    margin-left: 3px;
}

</style>
