<template>
	<view class="container">
		<view class="adressItem">
			<view class="adressCon">
				<view class="adressUp">
					<view class="adressUp_name">
						<text>老铁</text> <text>215415616546</text>
					</view>
					<view class="adressUp_default">
						默认
					</view>	
				</view>
				<view class="adressTxt">
					广东省-深圳市-福田区 深南大道1111号无名摩登大厦6楼A2
				</view>
			</view>
			<view class="adressIcon">
				<view class="icon icon-bianji"></view>
			</view>
		</view>
		<button class="addAddress" @click="navToAdressEditPage">新增地址</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			navToAdressEditPage() {
				uni.navigateTo({
					url: `/pages/adress/adressEdit`
				})
			}
		}
	}
</script>

<style lang="scss">
	.icon-bianji{
		position: relative;
		top: 50%;
		transform: translateY(-50%);
	}
.addAddress{
		position: fixed;
		left: 30upx;
		right: 30upx;
		bottom: 16upx;
		z-index: 95;
		display: flex;
		align-items: center;
		justify-content: center;
		width: 690upx;
		height: 80upx;
		font-size: 32upx;
		color: #fff;
		background-color: #FEB405;
		border-radius: 10upx;
		box-shadow: 1px 2px 5px rgba(219, 63, 96, 0.4);	
	}
.adressItem{
	background: #ffffff;
	display: flex;
	padding: 20upx 30upx;
	border-bottom: 1px solid #eeeeee;
}
.adressCon{
	width: 90%;	
	.adressUp{
		display: flex;
	 .adressUp_default{
			width: 30px;
			height: 14px;
			 font-size: 18upx;
			 border: 1px solid #FEB405;
			line-height: 14px;
			text-align: center;
			margin-top: 15upx;
		}
	}
		.adressTxt{
		font-size: 24upx;
		color: #777777;
	}
}
.adressUp_name{
	font-size: 34upx;
	margin-bottom: 15upx;
	 text:last-child{
		 	font-size: 24upx;
			margin: 0 20upx;
			
	 }
	

}
.adressIcon{
	width: 10%;	
	margin-left: 30upx;
	text-align: center;
	image{
		width: 60upx;
		height: 60upx;
		position: relative;
		top: 50%;
		transform: translateY(-50%);
	}
}
</style>
