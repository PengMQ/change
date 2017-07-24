<template>
  <div class="hello">
    <div class="img-process-section">
      <img src="./img/demohead.png" alt="head" id="imgHead" class="img-head">
      <img src="./img/demobg.png" alt="bg" class="img-bg" id="imgBg">
      <div class="canvas-container">
        <canvas id="palette" width="750px" height="1334px">your browser does not support canvas</canvas>
      </div>
    </div>
    <div class="img-present">
      <img src="" alt="" id="targetImg">
    </div>

    <button v-on:click="draw">draw</button>

  </div>
</template>

<script>
  export default {
    name: 'hello',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    mounted: function () {
    },
    methods: {
      draw: function () {
        var palette = document.querySelector('#palette');
        if (palette.getContext) {
          var context = palette.getContext('2d');
          var imgBg = document.querySelector('#imgBg');
          var imgHead = document.querySelector('#imgHead');
          context.drawImage(imgBg, 0, 0);

          context.drawImage(imgHead, 310, 29);
          context.drawImage(imgHead, 52, 306);
          context.drawImage(imgHead, 500, 306);
          context.drawImage(imgHead, 300, 570);
          context.drawImage(imgHead, 754, 615);
          context.drawImage(imgHead, 52, 828);
          context.drawImage(imgHead, 500, 828);
          context.drawImage(imgHead, 310, 1100);

          var imgUrl = palette.toDataURL('image/png');
          var targetImg = document.querySelector('#targetImg');
          targetImg.src = imgUrl;
        }

      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .img-head, .img-bg, #palette {
    position: absolute;
    visibility: hidden;
  }

  .canvas-container {
    border: 1px solid green;
    width: 100%;
    height: 100%;
  }

  #palette {
    width: 100%;
  }

  button {
    font-size: 25px;
    border: 1px solid;
    padding: 10px;
  }

</style>
