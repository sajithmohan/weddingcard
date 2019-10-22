<template>
  <div id="footer">
    <div>
      <i class="material-icons-outlined">
      home
      </i>
    </div>
    <div>
      <i class="material-icons-outlined">
      search
      </i>
    </div>
    <div>
      <i class="material-icons-outlined">
      add_box
      </i>
    </div>
    <div>
      <i class="material-icons-outlined">
      favorite_border
      </i>
    </div>
    <div>
      <i class="material-icons-outlined">
      person
      </i>
    </div>
  </div>
</template>
<script>
export default {

}
</script>
<style>
  #footer{
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    height: 50px;
    max-width: 500px;
    margin: auto;
    background: white;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    text-align: center;
    box-shadow: 0px -2px #EBEDEF;
  }
  #footer div {
    padding-top: 15px;
  }
</style>
