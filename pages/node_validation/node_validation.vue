<template>
	<view class="content">
		<view class="title">
			<u-icon name="map-fill" color="#FE7B41"></u-icon>
			<text>当前位置: 西湖景区门口</text>
			<text class="show_time">2023-6-5 10:00</text>
		</view>
		<u-search shape="round" placeholder="海口市前往三亚"></u-search>
		<view class="title">备注说明</view>
		<textarea placeholder="请输入备注说明......"></textarea>
		<button form-type="submit">确认提交</button>
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
		display: flex;
		flex-direction: column;
		margin: 20rpx;

		.title {
			display: flex;
			flex-direction: row;
			align-items: center;
			margin-top: 15rpx;
			margin-bottom: 15rpx;

			.u-icon {
				margin-left: 10rpx;
				margin-right: 10rpx;
			}

			.show_time {
				margin-left: 180rpx;
				font-size: 24rpx;
				color: #6E6E6E;
			}
		}
		
		textarea {
			width: 690rpx;
			// background: #FCFCFC;
			border: 2px solid #F2F2F2;
			border-radius: 15rpx;
			margin-top: 15rpx;
		}
		
		button{
			width: 260rpx;
			margin-top: 30rpx;
			border-radius: 15rpx;
			background-color: #FF5303;
			color: #FFFFFF;
		}
	}
</style>