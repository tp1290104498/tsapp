<template>
  <view class="user">
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
    <view  class="user-header">
      <view  class="header-icon" @click="upfile()">
        <image  src="./../../static/img/1.webp" ></image>
      </view>
    </view>
    <view  class="modify-user-info">
      <view  class="item-info">
        <view  class="item-icon">
          <image  src="./../../static/img/ID.png" alt="" title=""></image>
        </view>
        <p >ID</p>
        <span >94178</span>
      </view>
      <view  class="item-info">
        <view  class="item-icon">
          <image  src="./../../static/img/nc.png" alt="" title=""></image>
        </view>
        <p >昵称</p>
        <input  placeholder="填入昵称" class="input-box" disabled="disabled" value="天天">
      </view>
      <view  class="item-info">
      <view  class="item-icon">
        <image  src="./../../static/img/dlzh.png" alt="" title=""></image>
      </view>
        <p >登录账号</p>
        <input  placeholder="填入登录账号" class="input-box" >
      </view>
      <view class="item-info">
        <view class="item-icon">
          <image src="./../../static/img/mm.png" alt="" title=""></image>
        </view>
        <p >登录密码</p>
        <input  type="password" placeholder="密码长度必须大于6位" class="input-box">
      </view>
      <view class="item-info">
        <view  class="item-icon">
          <image src="./../../static/img/mm.png" alt="" title=""></image>
        </view>
        <p data-v-80252fe6="">确认密码</p>
        <input type="password" placeholder="重复输入上面的密码" class="input-box">
      </view>
    </view>
    <view  class="modify-poptip">
      <view  class="item-poptip">
        <p >登录账号设置成功以后不可以修改，ID不可以修改</p>
      </view>
      <view  class="item-poptip">
        <p >如果是微信扫码登录的，则此处为绑定账号</p>
      </view>
      <view  class="item-poptip">
        <p >绑定成功以后，扫码和账号登录则为同一账号，同一ID。</p>
      </view>
      <view  class="item-poptip">
        <p >为了更好的使用体验，建议使用APP访问。</p>
      </view>
    </view>
  </view>
</template>
<script>
export default {
  name: 'user',
  methods: {
    goblick() {
      uni.switchTab({
        url: '/pages/personage/index'
      });
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
.user{
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
  .user-header{
    background-image: url("../../static/img/usertxbj.png");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    height: 200rpx;
    .header-icon{
      width: 136rpx;
      height: 136rpx;
      background-image: url("../../static/img/userkuan.png");
      background-repeat: no-repeat;
      background-size: 100% 100%;
      margin-right: 150rpx;
      image{
        margin-top: 3rpx;
        width: 130rpx;
        height: 130rpx;
        border-radius: 50%;
      }
    }
  }
  .modify-user-info{
    margin: 3rpx 6rpx;
    height: 488rpx;
    border: 2rpx solid #756dd5;
    .item-info{
      display: flex;
      align-items: center;
      height: 96rpx;
      line-height: 96rpx;
      border-bottom: 2rpx solid transparent;
      border-top: 0;
      border-image: url("./../../static/img/usertablebr.png") 30 30 stretch;
      .item-icon{
        display: flex;
        align-items: center;
        justify-content: center;
        width: 160rpx;
        image{
          width: 56rpx;
          height: 48rpx;
        }
      }
      span{
        margin-right: 68rpx;
        flex-grow: 1;
        text-align: right;
        background-color: transparent;
        border: none;
        outline: none;
      }
      .input-box{
        padding-right: 48rpx;
        box-sizing: border-box;
        flex-grow: 1;
        margin-right: 28rpx;
        text-align: right;
        border: none;
        outline: none;
        background-color: transparent;
      }
    }
  }
  .modify-poptip {
    margin-top: 10rpx;
    margin-left: 65rpx;
    text-align: left;
    font-size: 26rpx;
    color: #000;
    .item-poptip{
      position: relative;
      margin-bottom: 6rpx;
      text-align:left;
      font-size: 26rpx;
      color:#000;
      ::before{
        content: "";
        position: absolute;
        top: 4rpx;
        left: -40rpx;
        width: 36rpx;
        height: 36rpx;
        margin-right: 20rpx;
        background-image: url("./../../static/img/listbj.png");
        background-size: 100% 100%;
      }
    }
  }
}
</style>
