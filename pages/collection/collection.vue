<template>
	<view class="container">
		<view class="footMarkList">
			<view class="footMarkView">
				<view class="footMarkItem">
					<view class="footMarkItem_con" :class="[flag==true?'open':'close']" @touchstart="touchStart(index,$event)" @touchmove="touchMove(index,$event)" @touchend="touchEnd(index,$event)">
						<view class="footMarkItem_pic">
							<image src="//i2.ygimg.cn/pics/adidas/2019/101205275/101205275_01_mb.jpg?3" mode=""></image>
						</view>
						<view class="footMarkItem_txt">
							<view class="footMarkItem_title">
								OPPO K3[高配套餐]闪充全面屏拍照游戏智能手机OPPO K3[高配套餐]闪充全面屏拍照游戏智能手机OPPO K3[高配套餐]闪充全面屏拍照游戏智能手机OPPO K3[高配套餐]闪充全面屏拍照游戏智能手机
							</view>
							<view class="footMarkItem_Price">
								￥2998
							</view>
						</view>
					</view>
					<view class="footMarkItem_del">
						删除
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				theIndex:null,
				oldIndex:null,
				isStop:false,
				flag:false,
			}
		},
		methods: {
		touchStart(index,event){
			//多点触控不触发
			if(event.touches.length>1){
				this.isStop = true;
				return ;
			}
			this.oldIndex = this.theIndex;
			this.theIndex = null;
			//初始坐标
			this.initXY = [event.touches[0].pageX,event.touches[0].pageY];
		},
		touchMove(index,event){
			//多点触控不触发
			if(event.touches.length>1){
				this.isStop = true;
				return ;
			}
			let moveX = event.touches[0].pageX - this.initXY[0];
			let moveY = event.touches[0].pageY - this.initXY[1];
			
			if(this.isStop||Math.abs(moveX)<5){
				return ;
			}
			if (Math.abs(moveY) > Math.abs(moveX)){
				// 竖向滑动-不触发左滑效果
				this.isStop = true;
				return;
			}
			
			if(moveX<0){
				this.theIndex = index;
				this.isStop = true;
				this.flag= true;
			}else if(moveX>0){
				this.flag= false;
				if(this.theIndex!=null&&this.oldIndex==this.theIndex){
					this.oldIndex = index;
					this.theIndex = null;
					this.isStop = true;
					setTimeout(()=>{
						this.oldIndex = null;
					},150)
				}
			}
		},
		touchEnd(index,$event){
			//结束禁止触发效果
			this.isStop = false;
		},
			
		}
	}
</script>

<style lang="scss">
	.footMarkList{width: 100%;}
	.footMarkItem{
		width: 100%;
		height: 100px;
		display: flex;
		margin-bottom:10px;
		align-items: center;
		position: relative;
		overflow: hidden;
		.footMarkItem_con{
			@keyframes showMenu {
				0% {transform: translateX(0);}100% {transform: translateX(-28%);}
			}
			@keyframes closeMenu {
				0% {transform: translateX(-28%);}100% {transform: translateX(0);}
			}
			&.open{
				animation: showMenu 0.25s linear both;
			}
			&.close{
				animation: closeMenu 0.15s linear both;
			}
			background-color: #fff;
			position: absolute;
			width: 100%;
			padding: 0 0;
			height: 100%;
			z-index: 3;
			flex-wrap: nowrap;
			display:flex;
			.footMarkItem_pic{
				image{
					width: 100px;
					height: 100px;
				}
			}
			.footMarkItem_txt{
				width: 70%;
				margin-left: 13px;
				.footMarkItem_title{
					font-size: 14px;
					display: -webkit-box;
					-webkit-box-orient: vertical;
					-webkit-line-clamp: 2;
					overflow: hidden;
			
				}
				.footMarkItem_Price{
					font-size: 16px;
					margin-top: 20px;
				}
		}
		
	}
		.footMarkItem_del{
			position: absolute;
			width: 28%;
			height: 100%;
			right: 0;
			justify-content: center;
			align-items: center;
			background-color:#FEB405;
			color: #FFFFFF;
			z-index: 2;
			line-height: 100px;
			text-align: center;
		}
	}
	.footMarkView{
		background: #FFFFFF;
		padding: 0 10px;
		margin-bottom:10px;
	}

	
</style>
