<template>
	<view class="container">
		<view class="integralHead">
			<view class="integralHead_txt">
				<text>当前积分</text>
			</view>
			<view class="integralHead_number">
				0
			</view>
		</view>
		<view class="integralCon">
			<view class="integralCon_mx">
				明细
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
.integralHead{
	width: 100%;
	height: 100px;
	background-color: #FEB405;
	padding: 15px;
	.integralHead_txt{
		font-size: 14px;
		margin-bottom: 20px;
	}
	.integralHead_number{
		width: 100%;
		text-align:center;
		font-size: 30px;
		
	}
}
.integralCon{
	width: 100%;
	.integralCon_mx{
		width: 100%;
		font-size: 12px;
		background: #F1F1F1;
		height: 20px;
		line-height: 20px;
		padding: 0 15px;
	}
}

</style>
