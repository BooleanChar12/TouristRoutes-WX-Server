<template>
	<view class="content">
		<view class="title">旅行团人员名单</view>
		<textarea placeholder="请填写备注......"></textarea>
		<view class="tag_list"> 标签: </view>
		<view class="tag" v-for="(item,id) in tagList" :key="id">
			<button>{{item}}</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tagList: ['夏日避暑', '度假胜地']
			};
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		margin: 15rpx;

		.title {
			margin: 15rpx;
			font-weight: bold;
		}
		textarea {
			width: 690rpx;
			margin: 15rpx;
			border: 1rpx solid #F2F2F2;
		}

		.tag_list {
			display: flex;
			align-items: center;
			width: 690rpx;
			height: 60rpx;
			margin: 15rpx;
			border: 1rpx solid #F2F2F2;
			border-radius: 15rpx;
		}

		.tag {
			display: flex;
			flex-direction: row;
			margin: 15rpx;
			button {
				display: flex;
				align-items: center;
				justify-content: center;
				width: 190rpx;
				height: 50rpx;
				border-radius: 30rpx;
				color: #F2F2F2;
				background-color: #999999;
			}
		}
	}
</style>