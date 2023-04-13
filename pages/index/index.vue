<template>
	<view class="container">
		<view class="title">
			星际引力
		</view>
		<view style="font-size: 25px;margin-top: 20px;margin-bottom: 20px;">
			引力系数测量站
		</view>

		<uni-card style="width: 600rpx;">
			<uni-forms ref="form" :model="formData" :rules="rules">
				<uni-forms-item label="姓名" name="name">
					<uni-easyinput v-model="formData.name" placeholder="请输入您的姓名" />
				</uni-forms-item>
				<uni-forms-item label="电话" name="phone">
					<uni-easyinput v-model="formData.phone" placeholder="请输入您的电话" />
				</uni-forms-item>
				<button @click="submit()">查询队友</button>
			</uni-forms>
		</uni-card>
		
		<uni-card v-if="check" style="width: 600rpx;">
			<view style="display: flex;align-items: center;justify-content: center;">
				<text style="font-size: 20px;">查询结果</text>
			</view>
			<view style="margin-top: 20px;">
				<text>您的小队成员是:</text>
				<view>
					<text>①姓名：</text> <text>{{ res.first.name }}</text>
				</view> 
				<view>
					<text>①电话：</text> <text>{{ res.first.phone }}</text>
				</view> 
				
				<view style="height: 1px; width: 500rpx;background-color: gray;margin-top: 10px;margin-bottom: 10px;margin-left: 10rpx;"></view>
				
				<view>
					<text>②姓名：</text> <text>{{ res.second.name}}</text>
				</view> 
				<view>
					<text>②电话：</text> <text>{{ res.second.phone }}</text>
				</view> 
			</view>
		</uni-card>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				check:false,
				formData: {
					name: "",
					phone: ""
				},
				rules: {
					name: {
						rules: [{
							required: true,
							errorMessage: "请输入您的姓名啊啊"
						}]
					},
					phone: {
						rules: [{
							required: true,
							errorMessage: "请输入电话号啊啊啊"
						}]
					}
				},
				res:{
					first:{
						name:"",
						phone:""
					},
					second:{
						name:"",
						phone:""
					}
				}
			}
		},
		methods: {
			submit() {
				uni.showLoading()
				this.$refs.form.validate().then(res => {
					uni.hideLoading()
					this.check = true
				}).catch(err => {
					uni.hideLoading()
					console.log('表单错误信息：', err);
				})
			}
		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.title{
		font-size: 40px;
	}
</style>