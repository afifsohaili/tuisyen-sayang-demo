<template>
  <div class="amin">
    <div class="head" v-on:keyup="move">
      <div class="eyes">
        <div class="eye">
          <div class="glass">
          </div>
        </div>
        <div class="eye">
          <div class="glass">
          </div>
        </div>
      </div>
      <div class="nose">
      </div>
      <div class="mouth">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    move: function (e) {
      console.log(e)
    }
  }
}
</script>

<style lang="scss">
.amin {
  display: block;
  margin: 0 auto;
  text-align: center;
  width: 30%;

  .head {
    background: radial-gradient(farthest-corner at top, #ffedb6 0%, #ffd65b 100%);
    border-radius: 400px;
    height: 300px;
    position: relative;
    width: 200px;
    border: 5px solid #000;
  }

  .eyes {
    position: absolute;
    top: 40%;
    left: 0;
    width: 100%;
  }

  .glass {
    position: absolute;
    background: rgba(white, 0.5);
    z-index: 1;
    width: 140%;
    height: 20px;
    left: calc(-20% - 1px);
    bottom: -10px;
    border-radius: 5px 5px 10px 10px;
    border: 2px solid #000;
  }

  .eye {
    background: white;
    border-radius: 30px;
    border: 5px solid #000;
    height: 30px;
    position: absolute;
    width: 30px;

    &:first-of-type {
      left: 15%;
    }

    &:last-of-type {
      right: 15%;
    }

    &:before {
      background: #000;
      border-radius: 10px;
      content: "";
      height: 20px;
      left: calc(50% - (20px / 2));
      position: absolute;
      top: calc(50% - (20px / 2));
      width: 20px;
    }

    &::after {
      border-top: 5px solid #000;
      content: "";
      left: -5px;
      position: absolute;
      top: -20px;
      width: 40px;
    }
  }

  .nose {
    border-radius: 20px;
    border: 3px solid darken(#ffedb6, 43%);
    height: 15px;
    left: calc(50% - 10px);
    position: absolute;
    top: 55%;
    width: 15px;

    &:after {
      background: radial-gradient(farthest-corner at bottom left, #ffedb6 0%, darken(#ffedb6, 17%) 100%);
      border-radius: 20px;
      content: "";
      height: calc(100% + 5px);
      left: -6px;
      position: absolute;
      top: -2px;
      width: calc(100% + 5px);
      z-index: 100;
    }
  }

  .mouth {
    background: red;
    position: absolute;
    top: 75%;
    border: 3px solid #000;
    left: calc(50% - (30px + 3px));
    height: 30px;
    width: 30px * 2;
    border-bottom-left-radius: 30px * 2;
    border-bottom-right-radius: 30px * 2;
  }
}

</style>
