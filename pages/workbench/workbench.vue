<template>
	<view class="content">
		<!-- v-model 用法 -->
		<uni-search-bar @confirm="search" :focus="true" v-model="searchValue" @blur="blur" @focus="focus" @input="input"
			@cancel="cancel" @change="change" @clear="clear"></uni-search-bar>
		<view class="cover">
			<image src="../../static/img/workbench/tu1 (1).png" mode="aspectFill"></image>
		</view>
		<view class="u-notice-bar">
			<u-notice-bar type="none" mode="horizontal" :list="notificationList" :more-icon="true"></u-notice-bar>
		</view>
		<view class="nav">
			<view v-for="(item,id) in navList" :key="id">
				<view class="nav-title" :class="{ activite: navIndex === id }" @click="checkId(id)">{{item}}</view>
			</view>
			<view class="uni-search-bar">
				<uni-search-bar class="uni-mt-10" radius="100" clearButton="auto" cancelButton="none" @confirm="search" />
			</view>
		</view>
		<view class="box" v-if="navIndex==0">
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
		
		<view v-if="navIndex==1">
			<view class="box" v-if="navIndex==1">
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
	</view>
</template>

<script>
	export default {
		data() {
			return {
				searchValue:"",
				notificationList:["通知1","通知2"],
				navList:["待开始订单","全部订单"],
				navIndex:0
			}
		},
		onLoad() {

		},
		methods: {
			goToOrderIng() {
				uni.navigateTo({
					url: "/pages/order-ing/order-ing"
				})
			},
			search(res) {
				uni.showToast({
					title: '搜索：' + res.value,
					icon: 'none'
				})
			},
			input(res) {
				console.log('----input:', res)
			},
			clear(res) {
				uni.showToast({
					title: 'clear事件，清除值为：' + res.value,
					icon: 'none'
				})
			},
			blur(res) {
				uni.showToast({
					title: 'blur事件，输入值为：' + res.value,
					icon: 'none'
				})
			},
			focus(e) {
				uni.showToast({
					title: 'focus事件，输出值为：' + e.value,
					icon: 'none'
				})
			},
			cancel(res) {
				uni.showToast({
					title: '点击取消，输入值为：' + res.value,
					icon: 'none'
				})
			},
			checkId(id){
				this.navIndex = id
			}
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		margin: 20rpx;
		.cover {
			image {
				width: 700rpx;
			}
		}
		.u-notice-bar{
			margin-top: 15rpx;
			margin-bottom: 15rpx;
		}
		
		.nav{
			display: flex;
			flex-direction: row;
			align-items: center;
			.nav-title{
				margin: 20rpx;
				font-size: 24rpx;
			}
			.nav-title.activite {
			    border-bottom: 4rpx solid #FE7B41;
			  }
			.uni-search-bar{
				width: 400rpx;
			}
		}

		.box {
			width: 690rpx;
			background: #FCFCFC;
			border: 2px solid #F2F2F2; // 边框 尺寸 样式（实线） 颜色
			border-radius: 15rpx; // 边框圆角半径
			display: flex;
			margin-bottom: 20px;
			flex-direction: row;
			/* 将布局改为行方向 */
			align-items: center;

			.box-img {
				image {
					width: 280rpx;
					height: 270rpx;
					margin: 15rpx;
				}
			}

			.box-content {
				margin: 15rpx;
				flex-direction: column;

				.abstract {
					font-size: 20rpx;
					margin-top: 20rpx;
					color: #6E6E6E;
				}

				.message {
					display: flex;
					flex-direction: row;
					margin-top: 25rpx;
					font-size: 25rpx;

					view {
						margin-right: 35rpx;
					}
				}

				.other {
					display: flex;
					flex-direction: row;
					margin-top: 25rpx;

					.money {
						margin-top: 11rpx;
						margin-right: 25rpx;
						color: #FE7B41;
						font-size: 23rpx;
					}

					.button {
						button {
							display: flex;
							align-items: center;
							justify-content: center;
							width: 160rpx;
							height: 53rpx;
							font-size: 23rpx;
							background-color: #FF5303;
							color: #FFFFFF;
							border-radius: 30rpx;
						}
					}
				}
			}
		}
	}
</style>