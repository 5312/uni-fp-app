<template>
	<view class="upload">
		<view class="content">
			<!-- 主体表单 -->
			<u-form :model="form" ref="uForm">
				<u-form-item label-width='200' label="油品类型">
					<u-input v-model="form.type" type="select" :select-open='show' @tap="show = true" />
				</u-form-item>
				<u-form-item label-width='200' label="油品数量">
					<u-input type='number' v-model="form.intro" />
					<view v-slot="right">L</view>
				</u-form-item>
				<u-form-item label-width='200' label="购油日期">
					<u-input v-model="form.date" type="select" @click='calendar = true' :select-open='calendar' />
				</u-form-item>
				<u-form-item label-width='200' label="发票照片">
					<u-upload max-count="1" :auto-upload='false' :action="action" :file-list="fileList"></u-upload>
				</u-form-item>
				<view class="btn">
					<u-button size='medium' type="primary" @click="submit">上传</u-button>
				</view>
			</u-form>
			<!-- 类型 -->
			<u-select v-model="show" :list="list" @confirm='confirm'></u-select>
			<!-- 日历 -->
			<u-calendar v-model="calendar" :mode="mode" @change="change"></u-calendar>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 演示地址，请勿直接使用
				action: 'http://www.example.com/upload',
				fileList: [],
				form: {
					type: '',
					intro: '',
					date: ''
				},
				show: false,
				calendar:false,
				mode: 'date',
				list: [{
						value: '92',
						label: '92#汽油'
					},
					{
						value: '95',
						label: '95#汽油'
					}
				],

			}
		},
		components: {

		},
		methods: {
			confirm(e) {
				this.form.type = e[0].label
			},
			change(e){
				this.form.date = e.result
			},
			submit() {
				// let files = [];
				// // 通过filter，筛选出上传进度为100的文件(因为某些上传失败的文件，进度值不为100，这个是可选的操作)
				// files = this.$refs.uUpload.lists.filter(val => {
				// 	return val.progress == 100;
				// })
				this.$refs.uUpload.upload();
			}
		}
	}
</script>

<style scoped lang="scss">
	.content {
		padding: 100rpx;

		.btn {
			text-align: center;
			padding-top: 150rpx;
		}
	}
</style>
