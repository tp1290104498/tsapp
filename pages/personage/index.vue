<template>
	<view class="content" :style="fullHeight">
    <view class="personal-info">
      <navigator url="/pages/personage/user" open-type="navigate">
      <view class="user-info">
          <view class="header-item">
            <view class="user-header">
              <image src="./../../static/img/1.webp"></image>
            </view>
          </view>
        <view class="header-item header-center">
          <p class="header-item-p"><span>天天</span></p>
          <p> <span>娱乐部:唐商</span></p>
          <p><span>房间号：256164</span></p>
          <p class="header-item-p"><span>账号：</span><span>18235180039</span></p>
          <p class="header-item-p "><span>ID：</span><span>94178</span></p>
<!--          ssax-->
        </view>
      </view>
      </navigator>

      <view class="integral-info">
        <view class="integral-item">
          <p class="value">0</p>
          <p class="desc">剩余积分</p>
        </view>
        <view class="integral-item">
          <p class="value">0</p>
          <p class="desc">今日盈亏</p>
        </view>
        <view class="integral-item">
          <p class="value">0</p>
          <p class="desc">今日流水</p>
        </view>
      </view>
      <view class="personal-content-box">
        <view class="personal-content">
          <navigator url="/pages/personage/Receivingset" open-type="navigate">
            <view class="personal-item">
              <view class="personal-item-img bind-account"></view>
              <span >体现收款设置</span>
              <view class="p-turn-right"></view>
            </view>
          </navigator>
          <view class="personal-item" @click="open()">
            <view class="personal-item-img bind-kj"></view>
            <span >开奖图显示期数</span>
            <view class="p-turn-right"></view>
          </view>
		<navigator url="/pages/personage/Zhangchangerecord/Zhangchangerecord" open-type="navigate">
			  <view class="personal-item">
				<view class="personal-item-img bind-jl"></view>
				<span >账变记录</span>
				<view class="p-turn-right"></view>
			  </view>
		  </navigator>
      <navigator url="/pages/personage/recharge" open-type="navigate">
          <view class="personal-item">
            <view class="personal-item-img bind-cz"></view>
            <span >充值记录</span>
            <view class="p-turn-right"></view>
          </view>
      </navigator>
      <navigator url="/pages/personage/Showrecords">
          <view class="personal-item">
            <view class="personal-item-img bind-txjl"></view>
            <span >提现记录</span>
            <view class="p-turn-right"></view>
          </view>
      </navigator>
      <navigator url="/pages/personage/statements" open-type="navigate">
          <view class="personal-item">
            <view class="personal-item-img bind-bbiao"></view>
            <span>代理报表</span>
            <view class="p-turn-right"></view>
          </view>
      </navigator>
      <navigator url="/pages/personage/Bettingrecord" open-type="navigate">
          <view class="personal-item">
            <view class="personal-item-img bind-tzjl"></view>
            <span >投注记录</span>
            <view class="p-turn-right"></view>
          </view>
      </navigator>
          <view class="personal-item">
            <view class="personal-item-img bind-bbh"></view>
            <span >版本号</span>
            <view class="p-turn-right" style="background-image: none">1.0</view>
          </view>
          <view class="personal-item">
            <view class="personal-item-img bind-tc"></view>
            <span >退出房间</span>
            <view class="p-turn-right"></view>
          </view>
          <view class="personal-item">
            <view class="personal-item-img bind-qh"></view>
            <span >切换账号</span>
            <view class="p-turn-right"></view>
          </view>
        </view>
      </view>
    </view>
    <uni-popup ref="popup" type="center">
        <ul class="pop">
          <li v-for="(item,index) in list" :key="index" @click="listnum(index)">
            <span> {{item.title}}</span>
            <image v-if="showidnex === index" class="imgse" src="./../../static/img/zqxz.png" alt=""></image>
          </li>
        </ul>
    </uni-popup>
	</view>
</template>

<script>
import uniPopup from 'components/uni-popup/uni-popup.vue'
import uniPopupMessage from 'components/uni-popup/uni-popup-message.vue'
import uniPopupDialog from 'components/uni-popup/uni-popup-dialog.vue'
	export default {
    components: {
      uniPopup,
      uniPopupMessage,
      uniPopupDialog
    },
		data() {
			return {
        showidnex: 0,
				fullHeight: '',
        currentTabIndex: 1,
        list: [
          {
            title: '10期'
          },
          {
            title: '20期'
          },
          {
            title: '30期'
          }
        ]
			}
		},
		onLoad() {

		},
		methods: {
      gpuers(url) {
        uni.navigateTo({
          url: url
        });
      },
      listnum(index) {
        this.showidnex = index
      },
      open() {
        this.$refs.popup.open()
      }
		},
		mounted() {
			let that = this
			uni.getSystemInfo({
				success(res) {
					that.fullHeight = "height:" + res.windowHeight + "px";
				}
			})
		}
	}
</script>

<style lang="scss" scoped>
	.content{
		height: 100%;
		width: 100%;
    background-image: url("./../../static/img/bg.jpg");
    background-repeat: no-repeat;
		background-position: 0px 0px;
		background-size: 100% 100%;
		position: fixed;
		z-index: -10;
	}
  ul,li {
    list-style: none;
  }
  .personal-info{
    display: flex;
    width: 100%;
    background-size: 100% 100%;
    flex-direction: column;
    height: 100%;
    background-image: url("./../../static/img/bg.jpg");
      .user-info {
        -ms-flex-negative: 0;
        flex-shrink: 0;
        position: relative;
        height: 204rpx;
        background-image: url("./../../static/img/usergx.png");
        display: flex;
        width: 100%;
        background-size: 100% 100%;
      }
      .user-info::before{
        content: '';
        position: absolute;
        top: 25%;
        right: 10%;
        width: 86rpx;
        height: 114rpx;
        background-image: url("./../../static/img/jtssx.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
      }
      .header-item {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
        -ms-flex-direction: column;
        flex-direction: column;
        -webkit-box-align: start;
        -ms-flex-align: start;
        align-items: flex-start;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        justify-content: center;
        -ms-flex-negative: 0;
        flex-shrink: 0;
        font-size: 26rpx;
        color: #fff;
        text-align: center;
        .user-header {
          margin: 20rpx 30rpx;
          width: 128rpx;
          height: 128rpx;
          background-image: url("./../../static/img/userkuan.png");
          background-size: 100% 100%;
          background-repeat: no-repeat;
          image {
            margin-top: 4rpx;
            margin-left: 4rpx;
            width: 120rpx;
            height: 120rpx;
            border-radius: 50%;
          }
        }
        .header-center{
          .header-item-p {
            line-height: 26rpx;
            font-size: 26rpx;
            color: #fff;
          }

        }
        .ssax{
          margin-top: 10rpx;
          line-height: 26rpx;
          font-size: 30rpx!important;
          color: #7195f9!important;
        }
      }
      .integral-info{
        flex-shrink: 0;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        margin-top: 4rpx;
        width: 100%;
        height: 140rpx;
        background-image: -webkit-gradient(linear,left bottom,left top,from(#3d2279),to(#16003f)),-webkit-gradient(linear,left top,left bottom,from(#1c0e32),to(#1c0e32));
        background-image: linear-gradient(0deg,#3d2279,#16003f),linear-gradient(#1c0e32,#1c0e32);
        border: 2rpx solid #6e36b7;
        .integral-item {
          flex: 1 1 33%;
          .value {
            margin-top: 24rpx;
            font-size: 34rpx;
            color: #fdedbc;
            text-align: center;
            font-weight: 700;
          }
          .desc {
            text-align: center;
            font-size: 34rpx;
            background: -webkit-gradient(linear,left top,left bottom,from(#fff),color-stop(.4,#fff),to(#9799ff));
            background-clip: border-box;
            -webkit-background-clip: text;
            color: transparent;
            font-weight: 700;
          }
        }
      }
      .personal-content-box{
        -webkit-box-flex: 1;
        -ms-flex-positive: 1;
        flex-grow: 1;
        margin-bottom: 20rpx;
        overflow: auto;
        .personal-content {
          margin-top: 10rpx;
          .personal-item{
            display: flex;
            -webkit-box-align: center;
            -ms-flex-align: center;
            align-items: center;
            position: relative;
            margin: 20rpx 0 0;
            width: 100%;
            height: 82rpx;
            -webkit-box-sizing: border-box;
            box-sizing: border-box;
            background-image: url("./../../static/img/libj.png");
            background-size: 100% 100%;
            font-size: 34rpx;
            color: #f9f5ff;
            .bind-account{
              width: 57rpx;
              height: 39rpx;
              margin: 0 20rpx;
              background-image: url("./../../static/img/sk.png");
              background-repeat: no-repeat;
              background-size: 57rpx 39rpx;
            }
            .bind-kj{
              background-image: url("./../../static/img/kj.png");
              background-size: 54rpx 54rpx;
              width: 54rpx;
              height: 54rpx;
              margin: 0 20rpx;
              background-repeat: no-repeat;
            }
            .bind-jl{
              width: 59rpx;
              height: 50rpx;
              margin: 0 20rpx;
              background-image: url("./../../static/img/jl.png");
              background-repeat: no-repeat;
              background-size: 59rpx 50rpx;
            }
            .bind-cz{
              width: 57rpx;
              height: 51rpx;
              margin: 0 20rpx;
              background-image: url("./../../static/img/cz.png");
              background-repeat: no-repeat;
              background-size: 57rpx 51rpx;
            }
            .bind-txjl{
              width: 48rpx;
              height: 48rpx;
              margin: 0 20rpx;
              background-image: url("./../../static/img/txjl.png");
              background-repeat: no-repeat;
              background-size: 48rpx 48rpx;
            }
            .bind-bbiao{
              background-image: url("./../../static/img/baobiao.png");
              background-repeat: no-repeat;
              background-size: 56rpx 56rpx;
              width: 56rpx;
              height: 56rpx;
              margin: 0 20rpx;
            }
            .bind-tzjl{
              background-image: url("./../../static/img/tzjl.png");
              background-repeat: no-repeat;
              background-size: 56rpx 56rpx;
              width: 56rpx;
              height: 56rpx;
              margin: 0 20rpx;
            }
            .bind-bbh{
              background-image: url("./../../static/img/bbh.png");
              background-size: 55rpx 55rpx;
              background-repeat: no-repeat;
              width: 55rpx;
              height: 55rpx;
              margin: 0 20rpx;
            }
            .bind-tc{
              background-image: url("./../../static/img/tcxx.png");
              background-size: 37rpx 46rpx;
              background-repeat: no-repeat;
              width: 37rpx;
              height: 46rpx;
              margin: 0 20rpx;
            }
            .bind-qh{
              background-repeat: no-repeat;
              background-image: url("./../../static/img/qh.png");
              background-size: 54rpx 51rpx;
              width: 54rpx;
              height: 51rpx;
              margin: 0 20rpx;
            }
            span{
              -webkit-box-flex: 1;
              -ms-flex-positive: 1;
              flex-grow: 1;
              text-align: left;
            }
            .p-turn-right{
              width: 28rpx;
              height: 44rpx;
              position: absolute;
              top: 18rpx;
              right: 40rpx;
              background-image: url("./../../static/img/jtsml.png");
              background-repeat: no-repeat;
              background-size: 100% 100%;

            }
          }
        }
      }
    }
  .pop{
    width: 538rpx;
    height: 226rpx;
    background-color: #ffffff;
    border-radius: 10rpx;
    li{
      line-height: 70rpx;
      border-bottom: 1rpx solid #dcdcdc;
      font-size: 34rpx;
      color: #000;
      position: relative;
      margin: auto;
      text-align: center;
      .imgse{
        position: absolute;
        top: 8rpx;
        right: 20rpx;
        width: 58rpx;
        height: 58rpx;
      }
    }
  }
	.cl {
		zoom: 1
	}

	.cl:after {
		clear: both;
		display: block;
		visibility: hidden;
		height: 0;
		content: '\20'
	}
</style>
