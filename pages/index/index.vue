<template>
	<view class="container">
		<view class="title">
			星际引力
		</view>
		
		<uni-card>
			<uni-forms ref="form" :model="formData" :rules="rules">
				<uni-forms-item label="姓名" name="name">
					<uni-easyinput  v-model="formData.name" placeholder="请输入您的姓名" />
				</uni-forms-item>
				<uni-forms-item label="电话" name="phone">
					<uni-easyinput  v-model="formData.phone" placeholder="请输入您的电话" />
				</uni-forms-item>
				<button @click="submit()">查询队友</button>
			</uni-forms>
		</uni-card>>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				formData:{
					name:"",
					phone:""
				},
				rules:{
					name:{
						rules:[
							{
								required: true,
								errorMessage: "请输入您的姓名啊啊"
							}
						]
					},
					phone:{
						rules:[
							{
								required: true,
								errorMessage: "请输入电话号啊啊啊"
							}
						]
					}
				}
			}
		},
		methods: {
			submit(){
				uni.showLoading()
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
</style>
