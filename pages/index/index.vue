<template>
	<view class="content" :style="fullHeight">
		<view class="t-login">
			<view class="t-b">{{title}}</view>
			<form class="cl">
				<view class="t-a">
					<image src="@/static/img/sj.png"></image>
					<input name="phone" placeholder="请输入账号" />
				</view>
				<view class="t-a">
					<image src="@/static/img/yz.png"></image>
					<input name="code" type="password" placeholder="请输入密码" />
<!--					<view class="t-c">发送短信</view>-->
				</view>
				<view class="t-d">未注册的手机号验证后将自动注册</view>
				<button form-type="submit" @click="openinfo()">立即登录</button>
			</form>
			<view class="t-f">登录即同意<text>用户协议</text></view>
			<view class="t-e cl">
				<view class="t-g">
					<image src="@/static/img/wx.png"></image>
					<view>微信</view>
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
				title: '欢迎登录账号'
			}
		},
		onLoad() {

		},
		methods: {
      openinfo() {
        uni.switchTab({
          url: '/pages/home/index'
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
	.content{
		height: 100%;
		width: 100%;
		// background-image: url(../../static/img/bg.jpg);
		background-repeat: no-repeat;
		background-position: 0px 0px;
		background-size: 100% 100%;
		position: fixed;
		z-index: -10;
		.t-login{
			width: 600rpx;
			margin: 0 auto;
			font-size: 28rpx;
			color: #000;
		button {
			font-size: 28rpx;
			background: #000;
			color: #fff;
			height: 90rpx;
			line-height: 90rpx;
			border-radius: 50rpx
		}
		input {
			padding: 0 20rpx 0 120rpx;
			height: 90rpx;
			line-height: 90rpx;
			margin-bottom: 50rpx;
			background: #f4f4f4;
			font-size: 28rpx;
			border-radius: 50rpx
		}
		.t-a {
			position: relative
		}
		.t-a image {
			width: 40rpx;
			height: 40rpx;
			position: absolute;
			left: 40rpx;
			top: 28rpx;
			border-right: 2rpx solid #dedede;
			padding-right: 20rpx
		}
		.t-b {
			text-align: center;
			font-size: 46rpx;
			color: #000;
			padding: 100rpx 0
		}
		.t-c {
			position: absolute;
			right: 22rpx;
			top: 22rpx;
			background: #000;
			color: #fff;
			font-size: 24rpx;
			border-radius: 50rpx;
			height: 50rpx;
			line-height: 50rpx;
			padding: 0 25rpx
		}
		.t-d {
			text-align: center;
			color: #999;
			margin: 80rpx 0
		}
		.t-e {
			text-align: center;
			margin: 80rpx auto 0;
		}
		.t-g {
			//float: left;
			//width: 50%
		}
		.t-e image {
			width: 50rpx;
			height: 50rpx
		}
		.t-f {
			text-align: center;
			margin: 80rpx 0 0 0;
			color: #666
		}
		.t-f text {
			margin-left: 8rpx;
			color: #999
		}
		.uni-input-placeholder {
			color: #000
		}
	}
	}
	// .t-login {
	// 	width: 600rpx;
	// 	margin: 0 auto;
	// 	font-size: 28rpx;
	// 	color: #000
	// }


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
