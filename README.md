# lottie-miniprogram


uniapp小程序中使用:
<template>
  <canvas id="canvas" type="2d" style="width:500rpx;height:300rpx"></canvas>
</template>

<script>
  import lottie from './lottie-miniprogram';
  export default{
    mounted(){
      uni.createSelectorQuery().in(this).select('#canvas').node(res => {
            const canvas = res.node
            const context = canvas.getContext('2d');
            canvas.width=800
            canvas.height=700
            lottie.setup(canvas)
            ani=lottie.loadAnimation({
                rendererSettings: {
                    context,
                },
                loop: false,
                autoplay: true,
                animationData:require('./xxx/xx.json'),
            })
        }).exec()
    }
  }
</script>
