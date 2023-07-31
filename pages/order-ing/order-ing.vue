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
			<view class="meassage" @click="goToPersonnerlList()">
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
			<view class="description" @click="goToMap()">总进度 :50%</view>
		</view>

		<!-- 步骤条 -->
		<view class="box">
			<uv-steps current="1" active-color="#5A5A5A" inactive-color="#5A5A5A">
				<uv-steps-item title="第一天">
					<template v-slot:icon>
						<uv-icon name="checkmark-circle-fill" color="#75B544"></uv-icon>
					</template>
				</uv-steps-item>
				<uv-steps-item title="第二天">
					<template v-slot:icon>
						<uv-icon name="checkmark-circle-fill" color="#75B544"></uv-icon>
					</template>
				</uv-steps-item>
				<uv-steps-item title="第三天">
					<template v-slot:icon>
						<uv-icon name="more-circle-fill" color="#EAC95D"></uv-icon>
					</template>
				</uv-steps-item>
				<uv-steps-item title="完成">
					<template v-slot:icon>
						<uv-icon name="/static/img/order/jieshu.png"></uv-icon>
					</template>
				</uv-steps-item>
			</uv-steps>
		</view>

		<!-- 时间轴 -->
		<view class="box">
			<uv-collapse @change="change" @close="close" @open="open" :value="['0']" :border="false">
				<uv-collapse-item title="D1 海口-曼谷" name="0">
					<uv-steps current="1" dot="true" active-color="#75B544" inactive-color="#EAC95D" direction="column">
						<view class="timeline" v-for="(item,id) in timelineList" :key="id" @click="goToNodeValidation(id)">
							<uv-steps-item :title="item.title" :desc="item.time"></uv-steps-item>
							<text v-if="item.state=='已完成'" class="state_yes">{{item.state}}</text>
							<text v-if="item.state!='已完成'" class="state_not">{{item.state}}</text>
						</view>
					</uv-steps>
				</uv-collapse-item>
			</uv-collapse>
			<uv-collapse @change="change" @close="close" @open="open" :value="['0']" :border="false">
				<uv-collapse-item title="D2 曼谷-伦敦" name="1">
					<uv-steps current="1" dot="true" active-color="#75B544" inactive-color="#EAC95D" direction="column">
						<view class="timeline" v-for="item in timelineList" @click="goToNodeValidation(id)">
							<uv-steps-item :title="item.title" :desc="item.time"></uv-steps-item>
							<text v-if="item.state=='已完成'" class="state_yes">{{item.state}}</text>
							<text v-if="item.state!='已完成'" class="state_not">{{item.state}}</text>
						</view>
					</uv-steps>
				</uv-collapse-item>
			</uv-collapse>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				timelineList: [{
						time: "7:50",
						title: "接机车辆到达机场",
						state: "已完成"
					},
					{
						time: "8:00",
						title: "机场接机",
						state: "待确定|自动签到"
					},
					{
						time: "8:30",
						title: "旅行团签到",
						state: "待确定"
					},
					{
						time: "9:30",
						title: "到达景点1",
						state: "待确定"
					},
					{
						time: "10:00",
						title: "景点购票",
						state: "待确定"
					}
				]
			}
		},
		onLoad(option) {
			console.log(option.id)

		},
		methods: {
			open(e) {
				console.log('open', e)
			},
			close(e) {
				console.log('close', e)
			},
			change(e) {
				console.log('change', e)
			},
			goToNodeValidation(id) {
				const item = this.timelineList[id];
				uni.navigateTo({
					url: "/pages/node_validation/node_validation?id=" + encodeURIComponent(item.title)
				})
			},
			goToPersonnerlList(){
				uni.navigateTo({
					url:"/pages/personnel_list/personnel_list"
				})
			},
			goToMap(){
				uni.navigateTo({
					url:"/pages/map/map"
				})
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
			margin-top: 15rpx;

			.meassage {
				display: flex;
				flex-direction: row;
				align-items: center;
				// justify-content: center;
				margin-left: 5rpx;
			}

			.title {
				margin: 15rpx;
			}

			.description {
				margin: 15rpx;
				color: #6E6E6E;
				font-size: 25rpx;
			}

			.timeline {
				display: flex;
				flex-direction: row;
				margin-top: 20rpx;
				margin-left: 30rpx;

				.state_yes {
					color: #75B544;
				}

				.state_not {
					color: #EAC95D;
				}
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
				width: 140rpx;
				height: 43rpx;
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
			// margin-top: 10rpx;

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