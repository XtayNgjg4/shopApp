<template>
	<view class="container">
		<view class="setbox">
			<view class="setItem ">
				<view class="setItem_con clearfix">
					<text class="fl">个人资料</text><text class="setItem_jt fr">></text>
				</view>
			</view>
			<view class="setItem ">
				<view class="setItem_con clearfix">
					<text class="fl">消息推送</text>
					<switch checked color="#fa436a" @change="switchChange" class="fr" />
				</view>
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

<style lang="scss">
.setbox{margin-top: 20upx;width: 100%;}
.setItem{
	width: 100%;
	background-color: #ffffff;
	align-items: center;
	justify-content: space-between;
	.setItem_con{
			padding: 20upx 0;
		border-bottom: solid 1upx #eee;
		margin-left:30upx;
		text{
			font-size: 30rpx;
			color: #303133;
		}
		.setItem_jt{
			font-size: 32rpx;
		    color: #909399;
			font-style: normal;
			margin-right: 10upx;
		}
	}
}
</style>
