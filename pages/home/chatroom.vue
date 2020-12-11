<template>
  <view class="chatroom">
    <view  class="game-header normal">
      <view class="go-back" @click="goblick()" style="position: absolute;">
      </view>
      <view class="header-center">
        <p class="header-title">
          <span>[澳洲5](38人)</span>
        </p>
      </view>
      <view class="additional">
        <view  class="save-icon"></view>
      </view>
    </view>
    <view  class="game-info" >
      <view  class="info-perids">
        <p >50744028期</p>
      </view>
   <view  class="count-down" >
     <view  class="count-item">0</view>
     <view  class="count-item">2</view>
     <view class="count-item item-3">1</view>
     <view  class="count-item">9</view>
   </view>
      <view  class="play-video" style=""></view>
      <view  class="amount-info">
        <p >0.00</p>
        <p >剩余积分</p>
      </view>
      <view  class="flush-amount"></view>
    </view>
    <view class="indexdonme">
      <input :value="value" placeholder="请输入" @input="onInput" />
      <view class="submit-send"></view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'chatroom',
  data() {
    return{
      value: ''
    }
  },
  mounted() {

  },
  methods: {
    goblick() {
      uni.switchTab({
        url: '/pages/home/index'
      });
    },
    onInput(e) {
      this.value = e.detail.value
    }
  }
}
</script>
<style lang="scss" scoped>
  .chatroom{
    width: 100%;
    position: fixed;
    height: 100vh;
    background-color: #f2f2f2;
    .game-header {
      position: relative;
      -ms-flex-negative: 0;
      flex-shrink: 0;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      height: 100rpx;
      background-size: 100% 100%;
      .additional {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-align: center;
        -ms-flex-align: center;
        align-items: center;
        position: absolute;
        top: 0;
        right: 30rpx;
        height: 100%;
        z-index: 199;
      }
      .save-icon{
        width: 64rpx;
        height: 64rpx;
        background-image: url("../../static/img/rlsaj.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
    }
    .normal{
      background-image: url("../../static/img/userheader.png");
    }
    .go-back{
      position: absolute;
      top:0;
      left: 0;
      width: 134rpx;
      height: 100rpx;
      background-image: url("../../static/img/userback.png");
      background-repeat: no-repeat;
      background-size: 100% 100%;
    }
    .header-center {
      -webkit-box-flex: 1;
      -ms-flex-positive: 1;
      flex-grow: 1;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      -webkit-box-pack: center;
      -ms-flex-pack: center;
      justify-content: center;
      .header-title {
        -webkit-box-flex: 1;
        -ms-flex-positive: 1;
        flex-grow: 1;
        text-align: center;
        font-size: 26rpx;
        color: #fff;
        text-shadow: 0 4rpx 0 0 rgba(0,0,0,.75);
        .add-info {
          font-size: 26rpx;
        }
      }
    }
    .game-info::before{
      content: "";
      position: absolute;
      top: 8rpx;
      left: 0;
      width: 100%;
      height: 109.2rpx;
      background-image: url("./../../static/img/3.png");
      background-repeat: no-repeat;
      background-size: 100% 100%;
    }
    .game-info{
      height: 117rpx;
      background-image: url("./../../static/img/1568.png");
      background-size: 100% 100%;
      background-repeat: no-repeat;
      width: 100vw;
      position: relative;
      display: flex;
      flex-shrink: 0;
      .info-perids{
        position: absolute;
        top: 16rpx;
        left: 10rpx;
        height: 89rpx;
        width: 186rpx;
        background: url("./../../static/img/4.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
        p{
          margin-top: 2rpx;
          line-height: 52rpx;
          font-size: 30rpx;
          text-align: center;
          color: #fff;
        }
      }
      .count-down{
        display: flex;
        align-items: center;
        position: absolute;
        text-align: center;
        top: 26rpx;
        left: 230rpx;
        width: 195rpx;
        height: 66rpx;
        background-image: url("./../../static/img/6.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        .count-item{
          width: 42rpx;
          height: 66rpx;
          line-height: 66rpx;
          font-size: 42rpx;
          font-family: countDown;
          color: #fff;
          text-stroke: .3px #000;
          -webkit-text-stroke: .3px #000;
        }
        .item-3{
          margin-left: 20rpx;
        }
      }
      .play-video{
        position: absolute;
        top: 40rpx;
        left: 450rpx;
        width: 56rpx;
        height: 42rpx;
        background-image: url("./../../static/img/8.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        z-index: 10;
      }
      .amount-info{
        display: flex;
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
        -ms-flex-direction: column;
        flex-direction: column;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        justify-content: center;
        position: absolute;
        top: 0;
        left: 69%;
        width:164rpx;
        height: 100%;
        font-size: 28rpx;
        color: #ffcaca;
        z-index: 10;
        text-align: center;
      }
      .flush-amount{
        position: absolute;
        top: 32rpx;
        right: 16rpx;
        width: 48rpx;
        height: 48rpx;
        background-image: url("./../../static/img/10.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
      }
    }
    .indexdonme{
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      background: url("../../static/img/11.png");
      background-repeat: no-repeat;
      background-size: 100% 100%;
      height: 96rpx;
      input{
        height: 80rpx;
        margin-top: 8rpx;
        margin-left: 10rpx;
        line-height: 80rpx;
        color: red;
      }
      .submit-send{
        width: 126rpx;
        height: 96rpx;

      }
    }
  }
</style>
