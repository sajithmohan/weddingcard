<template>
  <div id="headMain">
    <div class="headMain-content">
      <div>
        <i class="material-icons-outlined">camera_alt</i>
      </div>
      <div>
       <span> Sajith Weds Chaitanya</span>
      </div>
      <div>
        <img class="imgcls" src="assets/igtv_opt.png" />
      </div>
      <div class="right-aligned-text">
        <i class="material-icons-outlined rotated">send</i>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data(){
    return {
      publicPath: process.env.BASE_URL
    }
  },
  computed:{
    dynamicFont(){
      return {
        fontSize: '40px'
      }
    }
  }
}
</script>
<style>
.right-aligned-text{
  text-align: right;
  padding-right: 5px;
}
#headMain {
  max-width: 500px;
  padding-top: 10px;
  box-shadow: 0px 3px #EBEDEF;
  position: fixed;
  top: 0px;
  z-index: 1;
}
#headMain {
 background-color: #F8F9F9;
}
.headMain-content {
  font-size: 8vw;
  line-height: 11vw;
  font-family: 'Lovers Quarrel', cursive;
  display: grid;
  grid-template-columns: 1fr 8fr 1fr 1fr;

}
.headMain-content i {
  line-height: 11vw;
}
.imgcls{
  height: 24px;
  vertical-align: middle;
  border-radius: 20px;
  margin-left: 23px;
}

.rotated {
    -webkit-transform: rotate(-30deg);
    -moz-transform: rotate(-30deg);
    -ms-transform: rotate(-30deg);
    -o-transform: rotate(-30deg);
    transform: rotate(-30deg);
}
@media screen and (min-width: 500px) {
  .headMain-content i {
    line-height: 40px;
  }
  .headMain-content {
    font-size: 40px;
    line-height: 40px;
    font-family: 'Lovers Quarrel', cursive;
  }
  .imgcls{
    height: 30px;
    vertical-align: middle;
    border-radius: 20px;
    margin-left: 23px;
  }
}
</style>
