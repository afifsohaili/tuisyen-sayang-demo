<template>
  <div class="cartoon" :style="style">
    <div class="head">
      <div class="eye">
        <div class="eyeball"></div>
      </div>
      <div class="eye" id="right">
        <div class="eyeball"></div>
      </div>
      <div class="eye-back"></div>
      <div class="nose"></div>
      <div class="smile"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['top', 'left'],
  computed: {
    style: function () {
      return {
        left: this.left,
        top: this.top
      }
    }
  }
}
</script>

<style scoped>
.cartoon{
  position: relative;
}

.head{
  height: 118px;
  width: 130px;
  border-radius: 50%;
  background-color: #03A6D7;
  border: 2px solid #000;
  animation-name: move;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  transform-origin: 50% 100% 0;
}

.eye{
  height: 30px;
  width: 25px;
  border-radius: 50%;
  background-color: #fff;
  border: 1px solid #333;
  position: relative;
  display: inline-block;
  margin-top: 20px;
  margin-left: 35px;
  z-index: 1000;
}

.eyeball{
  height: 5px;
  width: 3px;
  position: absolute;
  border: 3px solid #333;
  background-color: #fff;
  top: 35%;
  right: 0;
  border-radius: 50%;
}

#right{
  transform: rotate(180deg);
  margin-left: 0;
}

.eye-back{
  background-color: #fff;
  height: 87px;
  border-radius: 50%;
  position: relative;
  top: -21%;
  left: 7%;
  z-index: 5;
  width: 112px;
}

.nose{
  height: 15px;
  width: 15px;
  border-radius: 50%;
  background: red;
  background: -webkit-radial-gradient(#FFDFD8 7%, #DF0910 60%);
  position: absolute;
  bottom: 45%;
  z-index: 100;
  left: 56px;
  border: 1px solid;
}

.smile{
  position: relative;
}

.smile:before{
  content: "";
  position: absolute;
  border: 1px solid #333;
  left: 48%;
  height: 35px;
  top: -78px;
  z-index: 101;
}

.smile:after{
  content: "";
  border-bottom: 2px solid #333;
  width: 90px;
  position: absolute;
  top: -127px;
  z-index: 101;
  border-radius: 96px;
  left: 14%;
  height: 84px;
}

.locket{
  width: 100px;
  border: 1px solid #000;
  background-color: #B02141;
  height: 5px;
  position: absolute;
  left: 16px;
  border-radius: 38%;
  bottom: -4px;
}

.body{
  width: 100px;
  height: 70px;
  margin: 20px 0;
  background: #03A6D7;
  border-radius: 50% / 10%;
  position: absolute;
}

.body:before{
  content: '';
  position: absolute;
  top: 10%;
  bottom: 10%;
  right: -5%;
  left: -5%;
  background: inherit;
  border-radius: 5% / 50%;
}

@keyframes move {
  0% {transform: rotate(0deg);}
  25% {transform: rotate(-15deg);}
  50% {transform: rotate(0deg);}
  75% {transform: rotate(15deg);}
  100% {transform: rotate(0deg);}
}
</style>
