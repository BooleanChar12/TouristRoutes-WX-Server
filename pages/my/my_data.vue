<template>
	<view class="content">
		<view class="meassage">
			<view class="input">
				<text class="title">姓名</text>
				<input placeholder="请输入您的姓名" />
			</view>
			<view class="input">
				<text class="title">联系方式</text>
				<input placeholder="请输入您的联系方式" />
			</view>
			<view class="input">
				<text class="title">学历</text>
				<input placeholder="请输入您的学历" />
			</view>
		</view>
		<view class="parting_line"></view>
		<view class="media">
			<view class="my_img">
				<uni-file-picker limit="9" title="个人照片"></uni-file-picker>
			</view>
			<view class="my_video">
				<uni-file-picker limit="9" file-mediatype="video" title="个人视频"></uni-file-picker>
			</view>
		</view>
		<view class="parting_line"></view>
		<view class="meassage">
			<view class="input">
				<text class="title">座右铭</text>
				<input placeholder="请输入您的座右铭" />
			</view>
			<view class="input">
				<text class="title">自我介绍</text>
				<textarea placeholder="请输入您的自我介绍"></textarea>
			</view>
		</view>
		<button class="submit" form-type="submit">确认提交</button>
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

		.meassage {
			.input {
				display: flex;
				flex-direction: row;
				align-items: center;
				margin: 15rpx;

				.title {
					width: 150rpx;
					font-weight: bolder;
					font-size: 25rpx;
				}

				input {
					border: 2rpx solid #E5E5E5;
					border-radius: 30rpx;
					width: 500rpx;
					padding: 1rpx 15rpx 1rpx;
				}
				textarea{
					border: 2rpx solid #E5E5E5;
					border-radius: 30rpx;
					width: 500rpx;
					height: 300rpx;
					padding: 1rpx 15rpx 1rpx;
				}
			}
		}

		.parting_line {
			width: 100%;
			height: 4rpx;
			background-color: #E5E5E5;
			margin-top: 15rpx;
		}
		.media{
			.my_img{
				margin-top: 15rpx;
				font-weight: bolder;
			}
			.my_video{
				margin-top: 15rpx;
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