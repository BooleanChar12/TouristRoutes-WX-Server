<template>
	<view class="content">
		<view class="money">
			<view class="count">
				<view class="amount">
					<text>￥19800</text>
					<text>佣金金额</text>
				</view>
				<view class="useable">
					<text>￥9860</text>
					<text>待提现</text>
				</view>
			</view>
			<button class="button_money">申请提现</button>
		</view>
		<view class="meassage">
			<view class="title">佣金明细</view>
			<view class="box">
				<view class="sub_box">
					<view class="sub_title">订单编号:</view>
					<view class="sub_content">45678045</view>
					<view class="show_date">2023-6-1</view>
				</view>
				<view class="sub_box">
					<view class="sub_title">路线: </view>
					<view class="sub_content">三亚-曼谷-伦敦</view>
				</view>
				<view class="sub_box">
					<view class="sub_content">让你在三亚的旅途中少走路......</view>
					<view class="acount_money">+￥860</view>
				</view>
				<view class="sub_box">
					<view class="sub_title">8人 | 15天</view>
					<view class="show_date_message">2023-6-1接团</view>
				</view>
			</view>
			<view class="box">
				<view class="sub_box">
					<view class="sub_title">订单编号:</view>
					<view class="sub_content">45678032</view>
					<view class="show_date">2023-5-28</view>
				</view>
				<view class="sub_box">
					<view class="sub_title">路线: </view>
					<view class="sub_content">蒙古-黑龙江-漠河</view>
				</view>
				<view class="sub_box">
					<view class="sub_content">在中国北方，真切体会到冬季的浪漫</view>
					<view class="acount_money">+￥860</view>
				</view>
				<view class="sub_box">
					<view class="other">8人 | 12天</view>
					<view class="show_date_message">2023-5-28接团</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.content {
		.money {
			display: flex;
			flex-direction: column;
			align-items: center;
			background: #FF5303;
			height: 300rpx;
			border-radius: 0rpx 0rpx 480rpx 480rpx;

			.count {
				display: flex;
				flex-direction: row;
				align-items: center;

				.amount {
					display: flex;
					flex-direction: column;
					color: #FFFFFF;
					margin-bottom: 25rpx;

					text {
						margin-top: 25rpx;
					}
				}

				.useable {
					display: flex;
					flex-direction: column;
					color: #FFFFFF;
					margin-bottom: 25rpx;

					text {
						margin-left: 160rpx;
						margin-top: 25rpx;
					}
				}
			}

			.button_money {
				display: flex;
				align-items: center;
				justify-content: center;
				width: 200rpx;
				height: 70rpx;
				margin-top: 30rpx;
				border-radius: 15rpx;
				background-color: #FFFFFF;
				color: #FF5303;
			}
		}

		.meassage {
			.title {
				margin: 20rpx;
			}

			.box {
				display: flex;
				flex-direction: column;
				width: 690rpx;
				background: #FCFCFC;
				border: 2px solid #F2F2F2;
				border-radius: 15rpx;
				display: flex;
				margin: 20rpx;
				padding:  15rpx 15rpx 15rpx 15rpx;
				.sub_box {
					display: flex;
					flex-direction: row;
					align-items: center;
					.sub_title{
						margin-left: 15rpx;
						margin-top: 15rpx;
					}
					.sub_content{
						font-size: 23rpx;
						color: #6E6E6E;
						margin-top: 15rpx;
						margin-left: 15rpx;
						
					}
					.show_date{
						font-size: 23rpx;
						color: #6E6E6E;
						margin-top: 15rpx;
						margin-left: 300rpx;
					}
					
					.other{
						margin-left: 15rpx;
						margin-top: 15rpx;
					}
					.show_date_message{
						margin-top: 15rpx;
						margin-left: 100rpx;
					}
					
					.abstract{
						font-size: 23rpx;
						color: #6E6E6E;
						margin-top: 15rpx;
						width: 350rpx;
					}
					.acount_money{
						color: #FF5303;
						margin-top: 15rpx;
						margin-left: 200rpx;
						font-weight: bolder;
					}
				}

			}
		}
	}
</style>