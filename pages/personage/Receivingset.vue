<template>
  <view class="Receivingset">
    <view  class="game-header normal">
      <view class="go-back" @click="goblick()" style="position: absolute;">
      </view>
      <view class="header-center">
        <p class="header-title">
          <span>账户设置</span>
        </p>
      </view>
      <view class="additional">
        <view  class="save-icon"></view>
      </view>
    </view>
    <view  class="bind-acc-list">
      <view  class="bind-item">
        <span  class="account-type-poptip">账户类型</span>
        <view class="uni-list">
          <view class="uni-list-cell">
            <view class="uni-list-cell-db">
              <picker @change="bindPickerChange" :value="index" :range="array">
                <view class="uni-input">{{array[index]}}</view>
              </picker>
            </view>
          </view>
        </view>
      </view>
      <view class="bind-item">
        <span class="account-type-poptip">账号号码</span>
        <input  placeholder="请填写收款人账户" class="account-value">
      </view>
      <view class="bind-item">
        <span  class="account-type-poptip">二维码</span>
        <view class="uplutsx" @click="upfile()">
            点击上传
        </view>
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'Receivingset',
  data(){
    return {
      array: [
        '支付宝',
        '微信'
      ],
      index: 0
    }
  },
  methods: {
    goblick() {
      uni.switchTab({
        url: '/pages/personage/index'
      });
    },
    bindPickerChange: function(e) {
      this.index = e.target.value
    },
    upfile() {
      let that = this
      uni.chooseImage({
        count: 1,
        sizeType: ['original','compressed'],
        success: (res) => {
          console.log(res.tempFilePaths[0]);
        }
      })
    }
  }
}
</script>
<style lang="scss" scoped>
  .Receivingset{
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
        right: 0;
        height: 100%;
        z-index: 199;
      }
      .save-icon{
        width: 162rpx;
        height: 64rpx;
        background-image: url("../../static/img/userbc.png");
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
    .bind-acc-list{
      position: relative;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      margin:40rpx;
      padding-bottom: 30rpx;
      border: 1px solid #080047;
      .bind-item{
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-pack: distribute;
        justify-content: space-around;
        margin-top: 26rpx;
        .account-type-poptip{
          width: 214rpx;
          font-size: 26rpx;
          color: #180244;
          margin-top: 20rpx;
          font-weight: 700;
        }
        .account-type, .uni-list{
          position: relative;
          width: 338rpx;
          height: 70rpx;
          line-height: 70rpx;
          font-size: 26rpx;
          color: #0048ff;
          border: 1px solid #080047;
          ::after{
            content: "";
            position: absolute;
            top: 20rpx;
            right: 20rpx;
            width: 50rpx;
            height: 30rpx;
            background-image: url("../../static/img/xjt.png");
            background-repeat: no-repeat;
            background-size: 100% 100%;

          }

          .uni-input{
            border: 1px solid #080047;
          }
        }
        .account-value{
          position: relative;
          width: 338rpx;
          height: 70rpx;
          line-height: 70rpx;
          font-size: 26rpx;
          color: #0048ff;
          border: 1px solid #080047;
        }
      }
      .uni-input{
        text-align: center;
      }
      .uplutsx{
        position: relative;
        width: 338rpx;
        height: 70rpx;
        line-height: 70rpx;
        font-size: 26rpx;
        color: #0048ff;
        border: 1px solid #080047;
        text-align: center;
        background-color: #333333;
      }
    }
  }
</style>
