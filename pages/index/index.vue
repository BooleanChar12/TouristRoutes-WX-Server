<template>
	<view class="content">
		<view class="box">
			<view class="box-img">
				<image src="/static/img/index/fengjing (1).png"></image>
			</view>
			<view class="box-content">
				<view class="title">暑期-夏日青海湖</view>
				<view class="abstract">热情的服务，路线安排的很合理；现在活动优惠力度和游玩...... </view>
				<view class="message">
					<view>5人 | 7天 </view>
					<view>2023-6-6接团</view>
				</view>
				<view class="other">
					<view class="money">总金额：￥680</view>
					<view class="button">
						<button @click="goToOrderIng">查看详情</button>
					</view>
				</view>
			</view>
		</view>
		<view class="box">
			<view class="box-img">
				<image src="/static/img/index/fengjing (2).png"></image>
			</view>
			<view class="box-content">
				<view class="title">都江堰避暑山庄</view>
				<view class="abstract">都江堰适合避暑的景区，山清水秀，远离城市喧嚣，适合自驾前往...... </view>
				<view class="message">
					<view>8人 | 15天</view>
					<view>2023-6-24接团</view>
				</view>
				<view class="other">
					<view class="money">总金额：￥1200</view>
					<view class="button">
						<button @click="goToOrderIng">查看详情</button>
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
				
			}
		},
		onLoad() {

		},
		methods: {
			goToOrderIng(){
				uni.navigateTo({
					url:"/pages/order-ing/order-ing"
				})
			}
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.box{
			width: 690rpx;
			background: #FCFCFC;
			border: 2px solid #F2F2F2; // 边框 尺寸 样式（实线） 颜色
			border-radius: 15rpx; // 边框圆角半径
			display: flex;
			margin-bottom: 20px;
			// flex-direction: row; /* 将布局改为行方向 */
			// align-items: center;
			.box-img{
				image{
					width:280rpx;
					height: 270rpx;
					margin: 15rpx;
				}
			}
			.box-content{
				margin: 15rpx;
				flex-direction: column;
				.abstract{
					font-size: 20rpx;
					margin-top: 25rpx;
					color:#6E6E6E;
				}
				.message{
					display: flex;
					flex-direction: row;
					margin-top: 25rpx;
					font-size: 26rpx;
					view{
						margin-right: 35rpx;
					}
				}
				.other{
					display: flex;
					flex-direction: row;
					margin-top: 25rpx;
					.money{
						margin-top: 11rpx;
						margin-right: 25rpx;
						color: #FE7B41;
						font-size: 23rpx;
					}
					.button{
						button{
							display: flex;
							align-items: center;
							justify-content: center;
							width: 160rpx;
							height: 53rpx;
							font-size: 23rpx;
							background-color:#FF5303;
							color:#FFFFFF;
							border-radius: 30rpx;
						}
					}
				}
			}
		}
	}
</style>
