<template>
	<view class="content">
		<view class="my_message">
			<image class="avatar" src="../../static/img/my/touxiang.png"></image>
			<view class="user_id">
				<text>VIP导游</text>
				<text>13800000888</text>
			</view>
			<view class="parting_line"></view>
			<view class="score">
				<text>480</text>
				<text>服务评分</text>
			</view>
			<view class="state">
				<text class="state_true" v-if="serviceState=='服务中'">{{serviceState}}</text>
				<text class="state_false" v-if="serviceState!='服务中'">{{serviceState}}</text>
			</view>
		</view>
		<view class="money" @click="goToMyMoney()">
			<view class="amount">
				<text>￥19800</text>
				<text>佣金金额</text>
			</view>
			<view class="useable">
				<text>￥9860</text>
				<text>待提现</text>
			</view>
		</view>
		<view class="my_list" v-for="(item,index) in myList" :key="index">
			<u-icon :name="item.icon"></u-icon>
			<uni-list class="uni-list" >
			    <uni-list-item showArrow :title="item.name" link :to="item.url" @click="($event,1)" ></uni-list-item>
			</uni-list>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				serviceState:'服务中',
				myList:[
					{
						name:"我的资料",
						icon:"/static/img/my/book-mark-fill.png",
						url:"/pages/my/my_data"
					},
					{
						name:"我的证书",
						icon:"/static/img/my/file-list-fill.png",
						url:"/pages/my/my_certificate"
					},
					{
						name:"服务记录",
						icon:"/static/img/my/file-history-fill.png",
						url:""
					},
					{
						name:"我的银行卡",
						icon:"/static/img/my/bank-card-2-fill.png",
						url:""
					},
					{
						name:"我的反馈",
						icon:"/static/img/my/draft-fill.png",
						url:""
					},
					{
						name:"我的信息",
						icon:"/static/img/my/notification-2-fill.png",
						url:""
					},
					{
						name:"设置",
						icon:"/static/img/my/settings-4-fill.png",
						url:""
					},
				]
			};
		},
		methods:{
			goToMyMoney(){
				uni.navigateTo({
					url:"/pages/my/my_money"
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
		display: flex;
		flex-direction: column;
		align-items: center;
		.my_message{
			display: flex;
			flex-direction: row;
			align-items: center;
			.avatar{
				width: 150rpx;
				height: 150rpx;
				border-radius: 50%; 
				margin: 15rpx;
			}
			.user_id{
				width: 180rpx;
				display: flex;
				flex-direction: column;
			}
			.parting_line{
				width: 50rpx;
				height: 180rpx;
				border-right: 4rpx solid  #E5E5E5;
			}
			.score{
				display: flex;
				flex-direction: column;
				width: 180rpx;
				margin-left: 30rpx;
				margin-right: 15rpx;
			}
			.state{
				.state_true{
					color: #FF5303;
				}
			}
		}
		
		.money{
			display: flex;
			flex-direction: row;
			align-items: center;
			width: 690rpx;
			background: #FF5303;
			border-radius: 30rpx;
			margin-top: 20rpx;
			margin-bottom: 20rpx;
			margin: 20prx;
			.amount{
				display: flex;
				flex-direction: column;
				color: #FFFFFF ;
				margin-bottom: 25rpx;
				text{
					margin-left: 160rpx;
					margin-top: 25rpx;
				}
			}
			.useable{
				display: flex;
				flex-direction: column;
				color: #FFFFFF ;
				margin-bottom: 25rpx;
				text{
					margin-left: 180rpx;
					margin-top: 25rpx;
				}
			}
		}
		
		.my_list{
			display: flex;
			flex-direction: row;
			align-items: center;
			.uni-list{
				width: 690rpx;
			}
		}

	}
</style>
