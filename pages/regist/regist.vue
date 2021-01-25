<template>
	<view class="page-wrap">
		<view class="login-box">
			<view class="inp-row">
				<view class="icon icon-user"></view>
				<input type="text" value="" class="account-inp" placeholder="请输入手机号码"/>
			</view>
			<view class="inp-row">
				<view class="icon icon-pwd"></view>
				<input type="password" value="" class="password-inp" placeholder="请输入密码"/>
			</view>
			<view class="inp-row">
				<input type="text" value="" class="code-inp" placeholder="请输入验证码"/>
				<button type="default" class="get-code">获取验证码</button>
			</view>
			<button type="default" class="login-btn">注册</button>
			<view class="bom">
				<text class="lf">已有账号</text>
				<navigator url="../../pages/login/login" hover-class="navigator-hover" class="navigator">
                    <text class="rg">点此登录</text>
                </navigator>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.page-wrap{
	width: 100%;
	height: 100vh;
	background: url('~@/static/login_bg_02.jpg') no-repeat;
	background-size: cover;
}
.login-box{
	width: 640rpx;
	background-color: #fff;
	margin: 0 auto;
	border-radius: 20rpx;
	position: relative;
	top: 280rpx;
	padding: 100rpx 40rpx 40rpx 40rpx;
	box-sizing: border-box;
}
.login-box .inp-row{
	width: 100%;
	height: 80rpx;
	border-radius: 40rpx;
	overflow: hidden;
	margin-bottom: 60rpx;
	position: relative;
}
.login-box .inp-row .icon{
	width: 48rpx;
	height: 48rpx;
	display: block;
	position: absolute;
	left: 20rpx;
	top: 16rpx;
}
.login-box .inp-row .icon-user{
	background: url('~@/static/icon_user.png') no-repeat;
	background-size: 100% 100%;
}
.login-box .inp-row .icon-pwd{
	background: url('~@/static/icon_pwd.png') no-repeat;
	background-size: 100% 100%;
}
.login-box .account-inp,
.login-box .password-inp{
	width: 100%;
	height: 80rpx;
	background-color: #eee;
	padding: 0 0 0 88rpx;
	box-sizing: border-box;
}
.login-box .code-inp{
	width: 48%;
	height: 80rpx;
	background-color: #eee;
	padding: 0 0 0 40rpx;
	box-sizing: border-box;
	border-radius: 40rpx;
}
.login-box .get-code{
	width: 48%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	color: #fff;
	font-size: 32rpx;
	background-color: #d1224b;
	border-radius: 40rpx;
	margin-left: 4%;
}
.login-box .code-inp,
.login-box .get-code{
	display: inline-block;
}
.login-btn{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	border-radius: 40rpx;
	margin: 0 auto;
	display: block;
	background-image: linear-gradient(45deg, #f1346d, #a3091b);
	color: #fff;
	font-size: 32rpx;
}
.bom{
	padding-top: 40rpx;
	font-size: 28rpx;
	color: #666;
	padding:20rpx;
	box-sizing: border-box;
	text-align: center;
}
.bom .rg{
	color: #d1224b;
}
.bom .navigator{
	display: inline-block;
}
</style>
