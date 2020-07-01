<template>
	<view class="">
		<view class="setbox">
			<view class="setItem ">
				<view class="setItem_con clearfix firstItem">
					<view >头像</view>
					<image src="../../static/logo.png" ></image>
					<text class="icon icon-you"></text>
				</view>
			</view>
			<view class="setItem ">
				<view class="setItem_con clearfix">
					<view >名称</view><text class="setItem_txt">xusSSnn</text>
				</view>
			</view>
			<view class="setItem ">
				<view class="setItem_con clearfix">
					<view >手机号码</view><text class="setItem_txt">1545284845</text>
				</view>
			</view>
			<button class="outLogin" @click="">退出登录</button>
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
	
<style lang="scss">
	.setItem_txt{
		font-size: 14px;
		margin: 0 8px;
	}
	.outLogin{
		align-items: center;
		justify-content: center;
		width: 90%;
		margin: 30px auto;
		height: 40px;
		font-size: 32upx;
		color: #fff;
		background-color: #FEB405;
		border-radius: 10upx;
		box-shadow: 1px 2px 5px rgba(219, 63, 96, 0.4);	
	}
	.firstItem view,.firstItem .icon-you{height: 50px;line-height: 50px;}
.setbox{width: 100%;}
.setItem{
	width: 100%;
	background-color: #ffffff;
	align-items: center;
	justify-content: space-between;

	.setItem_con{
		padding: 20upx 0;
		border-bottom: solid 1upx #eee;
		margin-left:30upx;
		display:flex;
		view{
			font-size: 30rpx;
			color: #303133;
			flex: 1;
		}
		.setItem_jt{
			font-size: 32rpx;
		    color: #909399;
			font-style: normal;
			margin-right: 10upx;
		}
		image{
			width: 100upx;
			height: 100upx;
			border-radius: 50%;
			margin-right: 30upx;
		}
	}
}
</style>
