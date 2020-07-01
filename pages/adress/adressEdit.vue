<template>
	<view class="container">
		<view class="adressEditBox">
			<view class="adressEditItme">
				<text>姓名</text>
				<input type="text" value="" />
			</view>
			<view class="adressEditItme ">
				<text class="switchtxt">设为默认</text>
				<switch  :checked="addressData.defaule" color="#fa436a" @change="switchChange" />
			</view>
		</view>
		<button class="addAddress" @click="">新增地址</button>
	</view>
</template>

<script>
</script>

<style lang="scss">
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
	.adressEditBox{
		width: 100%;
		background-color: #ffffff;
		margin-top: 20upx;
	}
	.adressEditItme{
		padding: 30upx;
		display: flex;
		border: 1px solid #eeeeee;
		.switchtxt{
			flex: 1;
		}
		text{
			font-size: 30upx;
			margin-right: 15upx;
		}
		input{
			flex: 1;
		}
		switch{
			transform: translateX(16upx) scale(.9);
		}
	}
</style>
