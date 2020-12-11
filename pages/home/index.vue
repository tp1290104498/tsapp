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
              <p> <span>娱乐部:唐商</span></p>
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
    <view class="centsnts">
      <ul>
        <li v-for="(item,index) in list" @click="GoLTSHI()" :class="item.class" :key="index">
          <span>{{item.title}}</span>
        </li>
      </ul>
    </view>
	</view>
</template>

<script>

	export default {
		data() {
			return {
				fullHeight: '',
        list: [
          {
            title: '澳洲5',
            class: 'li1'
          },
          {
            title:'澳洲10',
            class: 'li2'
          },
          {
            title: '极速时时彩',
            class: 'li3'
          },
          {
            title: '极速赛车',
            class: 'li4'
          },
          {
            title: '168飞艇',
            class: 'li5'
          },
          {
            title: '英国赛车',
            class: 'li6'
          },
          {
            title: '英国时时彩',
            class: 'li7'
          },
          {
            title: '英国极速赛车',
            class: 'li8'
          },
          {
            title: '英国极速时时彩',
            class: 'li9'
          },
        ]
			}
		},
		onLoad() {

		},
		methods: {
      GoLTSHI() {
        uni.navigateTo({
          url: '/pages/home/chatroom'
        })
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
		background-image: url("./../../static/img/bg.jpg");
		background-repeat: no-repeat;
		background-position: 0px 0px;
		background-size: 100% 100%;
		position: fixed;
		z-index: -10;
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
	}
  .centsnts{
    ul{
      margin-top: 30rpx;
      display: flex;
      //justify-content: space-around;
      flex-wrap: wrap;
      li{
        position: relative;
        width: 40%;
        margin: 0 2.5%;
        background-image: url("./../../static/img/listtp.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        height: 136rpx;
        text-align: center;
        color: #2e4af3;
        font-weight: 600;
        line-height: 136rpx;
        margin-top: 32rpx;
        span{
          display: inline-block;
          margin-top: 15rpx;
          font-size: 24rpx;
        }
      }
      .li1{
        background-image: url("./../../static/img/az5.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li2{
        background-image: url("./../../static/img/az10.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li3{
        background-image: url("./../../static/img/jsssc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li4{
        background-image: url("./../../static/img/jssc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li5{
        background-image: url("./../../static/img/168.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li6{
        background-image: url("./../../static/img/ygsc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li7{
        background-image: url("./../../static/img/ygssc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li8{
        background-image: url("./../../static/img/ygjssc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .li9{
        background-image: url("./../../static/img/ygjsssc.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
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
