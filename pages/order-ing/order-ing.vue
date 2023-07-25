<template>
	<view class="content">
		<view class="box">
			<view class="title">杭州西湖景观之旅</view>
			<view class="description">这次我们将前往的是江南名胜杭州西湖~，同城向导随行讲解，贴心服务，车接车送。</view>
		</view>
		<view class="tag">
			<button>标签1</button>
			<button>标签2</button>
			<button>标签3</button>
		</view>
		<view class="box">
			<view class="meassage">
				<view class="title">时间 :</view>
				<view class="description">2023-6—5~2023-6-7</view>
			</view>
			<view class="meassage">
				<view class="title">人数 :</view>
				<view class="description">5人</view>
			</view>
			<view class="meassage">
				<view class="title">司机 :</view>
				<view class="description">刘师傅136****5134</view>
			</view>
			<view class="meassage">
				<view class="title">酒店 :</view>
				<view class="description">喜来登酒店 010-8989*****</view>
			</view>
		</view>
		<view class="main-title">
			<view class="title">行程服务进度</view>
			<u-icon name="map" color="#6E6E6E"></u-icon>
			<view class="description">总进度 :50%</view>
		</view>
		<view class="box">

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		}
	}
</script>

<style lang="scss">
	@import "uview-ui/index.scss";
	.content {
		display: flex;
		flex-direction: column;
		margin: 20rpx;

		// align-items: center;
		// justify-content: center;
		.box {
			width: 690rpx;
			background: #FCFCFC;
			border: 2px solid #F2F2F2;
			border-radius: 15rpx;

			.meassage {
				display: flex;
				flex-direction: row;
				align-items: center;
				// justify-content: center;
				margin-left: 20rpx;
			}

			.title {
				margin: 20rpx;
			}

			.description {
				margin: 20rpx;
				color: #6E6E6E;
				font-size: 25rpx;
			}
		}

		.tag {
			display: flex;
			flex-direction: row;

			button {
				margin: 15rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				width: 160rpx;
				height: 53rpx;
				font-size: 25rpx;
				background-color: #FF5303;
				color: #FFFFFF;
				border-radius: 30rpx;
			}
		}

		.main-title {
			display: flex;
			flex-direction: row;
			align-items: center;
			margin-top: 10rpx;

			.title {
				margin: 20rpx;
				margin-right: 290rpx;
				font-weight: bold;
			}

			.description {
				margin: 13rpx;
				color: #6E6E6E;
			}
			image {
				width: 50rpx;
				height: 50rpx;
				margin-right: 1rpx;
			}
		}
	}
</style>