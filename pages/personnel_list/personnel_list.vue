<template>
	<view class="content">
		<view class="personnel" v-for="(item,id) in personnerList" :key="id">
			<view class="name">{{item.name}}</view>
			<view class="sex">{{item.sex}}</view>
			<view class="phone">{{item.phone}}</view>
			<view class="remark">{{item.remark}}</view>
			<button @click="goTopersonnerlListRemark()">添加备注</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				personnerList:[
					{
						name:"李桐安",
						sex:"男",
						phone:"137****3170",
						remark:"家人出行"
					},
					{
						name:"张晓楠",
						sex:"女",
						phone:"180****6852",
						remark:"夫妻出行"
					},
					{
						name:"何菱",
						sex:"女",
						phone:"135****8112",
						remark:"家人出行"
					},
					{
						name:"王岚平",
						sex:"男",
						phone:"132****6287",
						remark:"单人出行"
					},
					{
						name:"刘彦桉",
						sex:"男",
						phone:"182****0724",
						remark:"家人出行"
					},
					{
						name:"罗钰渊",
						sex:"男",
						phone:"137****3460",
						remark:"夫妻出行"
					}
				]
			};
		},
		methods:{
			goTopersonnerlListRemark(){
				uni.navigateTo({
					url:"/pages/personnel_list/personnerl_list_remark"
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
		display: flex;
		flex-direction: column;
		margin-left: 15rpx;
		.personnel{
			display: flex;
			flex-direction: row;
			align-items: center;
			margin: 15rpx;
			border-bottom: 1px solid #999999;
			.name{
				margin: 15rpx;
				width: 100rpx;
			}
			.sex{
				margin: 15rpx;
				color: #999999;
				width: 50rpx;
			}
			.phone{
				margin: 15rpx;
				color: #999999;
				width: 170rpx;
			}
			.remark{
				margin: 15rpx;
				color: #999999;
				width: 130rpx;
			}
			button{
				display: flex;
				align-items: center;
				// justify-content: center;
				font-size: 23rpx;
				background-color: #FF5303;
				color: #FFFFFF;
				border-radius: 30rpx;
				height: 40rpx;
			}
		}
	}
</style>
