<template>
	<view class="content" :style="fullHeight">
    <view class="headers">
      <view class="header-con">
        <view class="user-info">
          <view  class="header-item header-left">
            <view  class="user-header">
              <image  src="./../../static/img/1.webp" alt="user-header" title="user-header"></image>
            </view>
            <view  class="item-right">
              <p >天天</p>
              <p> <span>娱乐部:唐商 </span></p>
              <p >ID:94178</p>
            </view>
          </view>
          <view  class="header-item header-right">
            <view class="integral">
              <view class="lefticon"></view>
              <span>0</span>
              <view class="add-integral">
              </view>
            </view>
          </view>
        </view>
        <view  class="notice">
          <view class="notice-list">
            <view class="notice-item" style="display: none;">
              <view class="all-notice">

              </view>
            </view>
            <p  class="no-notice">暂无公告</p>
          </view>
        </view>
      </view>
    </view>
    <view class="centnst1">
        <view class="centheader">
          <image src="./../../static/img/KF.png"></image>
          <span>联系客服</span>
        </view>
      <view class="method-info">
        <view class="info-item">
          <image src="./../../static/img/wxxx.png"></image>
          <p class="account">暂未开放</p>
          <view class="info-copy">复制</view>
        </view>
        <view class="info-item">
          <image src="./../../static/img/QQx.png"></image>
          <p class="account">暂未开放</p>
          <view class="info-copy">复制</view>
        </view>
      </view>
    </view>
    <view class="centnst1">
      <view class="centheader">
        <image src="./../../static/img/sxf.png"></image>
        <span>上下分</span>
      </view>
      <view class="method">
        <ul  class="up-down-list">
          <li class="up-item" v-for="(item,index) in listtext" :key="index" @click="goindex(index)" :class="{avicet: shoindexn == index}">
            {{item.title}}
          </li>
        </ul>
        <view class="intext">
          <input type="number" placeholder="输入上下分金额(数字)">
        </view>
        <view class="btns">
          提交申请
        </view>
      </view>
    </view>
	</view>
</template>

<script>

	export default {
		data() {
			return {
				fullHeight: '',
        currentTabIndex: 1,
        shoindexn: 0,
        listtext: [
          {
            title: '上分'
          },
          {
            title: '下分'
          }
        ]
			}
		},
		onLoad() {

		},
		methods: {
      goindex(index) {
        this.shoindexn = index
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
ul,li{
  list-style: none;
}
	.content{
		height: 100%;
		width: 100%;
		background-repeat: no-repeat;
		background-position: 0px 0px;
		background-size: 100% 100%;
		position: fixed;
    background-image: url("./../../static/img/bg.jpg");

    z-index: -10;
	}
  .headers{
  height: 168rpx;
  width: 100%;
  //background: #cccccc;
  .header-con{
    background-image: url("./../../static/img/userbj.png");
    background-size: 100% 100%;
    background-repeat: no-repeat;
    .user-info{
      display: flex;
      .header-left{
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .header-item{
        display: flex;
        width: 396rpx;
        .user-header{
          width: 118rpx;
          height: 118rpx;
          margin: 0 20rpx;
          border-radius: 50%;
          background-repeat: no-repeat;
          background-image: url("./../../static/img/userkuan.png");
          background-size: 100% 100%;
          image{
            margin-top: 9rpx;
            margin-left: 9rpx;
            border-radius: 50%;
            width: 100rpx;
            height: 100rpx;
          }
        }
        .item-right{
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          padding-top: 10rpx;
          :first-child{
            color: #ffffff;
            line-height: 35rpx;
          }
          :last-child{
            color: #7195f9;
            line-height: 35rpx;
          }
        }
        .integral{
          position: relative;
          top: 26rpx;
          //padding: 0 .35rem;
          min-width: 186rpx;
          margin-left: 52rpx;
          height: 52rpx;
          line-height: 52rpx;
          background-color: #0b040e;
          -webkit-box-shadow: inset 0 2rpx 0 0 rgba(0,0,0,.75);
          box-shadow: inset 0 4rpx 0 0 rgba(0,0,0,.75);
          border-radius: 10rpx;
          border: 2rpx solid #849ee1;
          font-size: 32rpx;
          color: #ffffff;
          -webkit-box-sizing: border-box;
          box-sizing: border-box;
          text-align: center;
          .lefticon{
            content: "";
            position: absolute;
            top: -2%;
            left: -26rpx;
            width: 52rpx;
            height: 52rpx;
            background-image: url("./../../static/img/inputLeft.png");
            background-repeat: no-repeat;
            background-size: 100% 100%;
          }
          .add-integral{
            background-image: url("./../../static/img/addins.png");
            background-repeat: no-repeat;
            background-size: 100% 100%;
            width: 52rpx;
            height: 52rpx;
            right: -26rpx;
            top: -2%;
            position: absolute;
            ::before{
              background-image: none;
            }
          }
        }
      }
      .header-right{
        position: relative;
        right: 0rpx;
        top: 20rpx;
      }

    }
    .notice{
      background-image: url("./../../static/img/noticebj.png");
      background-repeat: no-repeat;
      background-size: 100% 100%;
      display: flex;
      border-top: 1rpx solid #0c70ac;
      align-items: center;
      position: relative;
      height: 50rpx;
      margin-top: 5rpx;
      color: #fff;
      box-sizing: border-box;
      z-index: 9999;
      ::before{
        content: "";
        width: 30rpx;
        height: 30rpx;
        background-image: url("./../../static/img/xx.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
        position: absolute;
        left: 50rpx;
        top: 10rpx;
      }
      .notice-list {
        margin-left: 50rpx;
        width: 100%;
        overflow: hidden;
        text-align: left;
        .no-notice {
          padding-left: 50rpx;
          text-align: center;
          p{
            font-size: 16rpx;
          }
        }
      }
    }
  }
}
  .centnst1{
    margin: 10rpx;
    height: 345rpx;
    border-radius: 10rpx;
    background-color: rgba(0,2,53,.5);
    border: 2rpx solid #898ac0;
    .centheader{
      height: 86rpx;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      -webkit-box-pack: start;
      -ms-flex-pack: start;
      justify-content: flex-start;
      padding: 0 36rpx;
      background-image: linear-gradient(90deg,#3a3790,#6471bc 25%,#8eaae8 50%,#35358a),linear-gradient(#6047c4,#6047c4);
      background-blend-mode: normal,normal;
      box-shadow: 0 4rpx 0 0 rgba(0,2,93,.51);
      -webkit-box-sizing: border-box;
      box-sizing: border-box;
      image{
        width: 60rpx;
        height: 60rpx;
      }
      span{
        margin-left: 20rpx;
        font-size: 36rpx;
        color: #fff;
        font-weight: 700;
      }
    }
    .method-info{
      .info-item {
        display: flex;
        align-items: center;
        justify-content: space-around;
        margin: 24rpx auto 0;
        padding: 0 24rpx;
        width: 89%;
        height: 100rpx;
        background-color: #4c4a8c;
        border-radius: 10rpx;
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
        image{
          width: 72rpx;
          height: 60rpx;
        }
        .account{
          line-height: 112rpx;
          height: 100rpx;
          color: #ffffff;
          font-weight: 700;
        }
        .info-copy{
          background-image: url("./../../static/img/btnbj.png");
          height: 66rpx;
          width: 166rpx;
          font-size: 40rpx;
          background-size: 100% 100%;
          letter-spacing: 4rpx;
          color: #ffffff;
          text-align: center;
          line-height: 60rpx;
        }
      }
      .info-item:nth-child(2){
        image{
          width: 66rpx;
          height: 72rpx;
        }
      }
    }
    .method{
      height: 245rpx;
      .up-down-list{
        height: 50rpx;
        display: flex;
        margin-top: 15rpx;
        //justify-content: space-around;
        .up-item{
          margin: 10rpx 0;
          width: 42%;
          height: 50rpx;
          background-image: linear-gradient(0deg,#646464,#bfbfbf 50%,#d7d7d7),linear-gradient(#baa9ff,#baa9ff);
          box-shadow: 0 .05rem .05rem 0 rgba(88,88,88,.75);
          border-image-source: linear-gradient(0deg,#898989 1%,#e3e3e3);
          text-align: center;
          line-height: 50rpx;
          font-size: 28rpx;
          color: #ffffff;
          font-weight: 700;
        }
        .avicet{
          background-image: linear-gradient(0deg,#7251b0,#9e6ad8 32%,#c982ff),linear-gradient(#baa9ff,#baa9ff);
          box-shadow: 0 .05rem .05rem 0 rgba(91,5,146,.75);
          border-image-source: linear-gradient(0deg,#9050d2 1%,#f578fd);
          text-shadow: 0 2rpx;
        }
      }
      .intext{
        height: 50rpx;
        width: 80%;
        margin: auto;
        margin-top: 40rpx;
        border-radius: 10rpx;
        border: 2rpx solid #fff;
        input{
          border-radius: 10rpx;
          width: 100%;
          height: 50rpx;
          color: #ffffff;
        }
      }
      .btns{
        height: 50rpx;
        width: 80%;
        margin: auto;
        margin-top: 20rpx;
        border-radius: 10rpx;
        border: 2rpx solid #fff;
        text-align: center;
        line-height: 50rpx;
        font-size: 26rpx;
        color: #ffffff;
        text-shadow: 0 2rpx;
        font-weight: 700;
        background-image: linear-gradient(0deg,#1e8c56,#77e599),linear-gradient(#fff,#fff);
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
