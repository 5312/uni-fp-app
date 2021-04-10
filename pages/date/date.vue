<template>
	<view class="date">
		<view class="list">
			<view class="item" v-for='x,y in list' :key='y'>
				<image src="../../static/fp.jpg" mode=""></image>
				<view class="right">
					<view>xxx</view>
					<view>xxx</view>
					<view>xxx</view>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						
					},
					{
						
					}
				]
			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
page{
	.date{
		.list{
			.item{
				display: flex;
				justify-content: start;
				align-items: center;
				padding:20rpx;
				border-bottom:1px solid #ddd;
				image{
					width:300rpx;
					height: 200rpx;
					margin-right:10rpx;
				}
				.right{
					
				}
			}
		}
	}
}
</style>
