<template>
	<view class="content">
		<view class="media">
			<view class="my_img">
				<uni-file-picker limit="9" title="旅行社经营许可证"></uni-file-picker>
			</view>
			<view class="my_img">
				<uni-file-picker limit="9" title="导游资格证"></uni-file-picker>
			</view>
			<view class="my_img">
				<uni-file-picker limit="9" title="其他证书"></uni-file-picker>
			</view>
		</view>
		<button class="submit" form-type="submit">提交审核</button>
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
	.content{
		display: flex;
		flex-direction: column;
		.media{
			margin: 15rpx;
			.my_img{
				border: 2rpx solid #E5E5E5;
				border-radius: 15rpx;
				margin: 15rpx;
				padding: 15rpx 15rpx 15rpx 15rpx;
				font-weight: bolder;
			}
		}
		.submit{
			display: flex;
			align-items: center;
			justify-content: center;
			width: 200rpx;
			height: 70rpx;
			margin-top: 30rpx;
			border-radius: 15rpx;
			background-color: #FF5303;
			color: #FFFFFF;
		}
	}
</style>
