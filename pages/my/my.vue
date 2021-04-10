<template>
	<view>
		<view class="personal">
			<view class="personal-main">
				<u-avatar :src="avatar" mode="square" size="120" class="u-avatar"></u-avatar>
				<view class="personal-info">
					<view class="">name</view>
					<view class="">id:12333333333</view>
				</view>
			</view>
			<u-icon name="arrow-right" size="30" class="p-right-icon"></u-icon>
		</view>
		<!-- <view class="detail">
			<view class="detail item" v-for="x,y in list" :key='y'>
				<view class="left">{{x.name}}:</view>
				<view class="right">{{x.value}}</view>
			</view>
		</view> -->
		<u-cell-group>
			<u-cell-item v-for='x,y in list' :key='y' :icon='x.icon' :title="x.name" :value='x.value' :arrow='false'></u-cell-item>
		</u-cell-group>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				avatar: '/static/header.png',
				list: [{
						name: '名称',
						value: 'xxx加油站',
						icon:'bookmark-fill'
					},
					{
						name: '地址',
						value: 'xxxxxxx',
						icon:'map-fill'
					},
					{
						name: '联系人',
						value: '张某',
						icon:'man-add-fill'
					},
					{
						name: '联系电话',
						value: '13333333333',
						icon:'phone-fill'
					}
				]
			}
		},
		methods: {
			onClick(item) {},
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #f7f7f7;

		.detail {
			background-color: #fff;

			.item {
				border-bottom: 1px solid #efefef;
				padding: 20rpx;
				font-size: 0;

				.left {
					font-size: 40rpx;
					display: inline-block;
					margin-right: 20rpx;
				}

				.right {
					font-size: 40rpx;
					display: inline-block;

				}
			}
		}
	}

	.personal {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 30rpx 0 40rpx 30rpx;
	}

	.personal-main {
		display: flex;
		align-items: center;
	}

	.personal-info {
		display: flex;
		flex-direction: column;
	}

	.u-avatar {
		margin-right: 30rpx;
	}

	.navbar-right {
		padding: 0 40rpx;
	}

	.navbar-right-icon {
		margin-left: 50rpx;
	}

	.hover-class {
		background-color: #efefef;
	}



	.p-right-icon {
		padding: 0 40rpx;
	}
</style>
