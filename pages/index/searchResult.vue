<template>
	<view class="content">
		<block v-for="item in searchList">
			<view class="">
				<image :src="item.mainPic" style="width: 200rpx;height: 200rpx;"></image>
			</view>
			
		</block>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				searchText:'',
				searchList:[]
				
			}
		},
		onLoad(event) {
			console.log(event.searchText);
			this.searchText=event.searchText;
			this.getSearchGoods();
			
		},
		methods: {
			getSearchGoods(){
				
				uni.request({
					url:'http://localhost/demo.php',
					data:this.searchText,
					method:'POST',
					success: (res) => {
						console.log(res.data.data.list);
						this.searchList=res.data.data.list;
						
					}
				})
				
				
			}
			
		}
	}
</script>

<style lang="scss">
	.content{
		
	}
	.hengbox{
		font-size: 50rpx;
		margin-top: 50rpx;
		margin-left: 50rpx;
		width: 200rpx;
		.mytxt{
			font-size: 80rpx;
			background-color: #DD524D ;
			
		}
		
		
		
	}
	

</style>
