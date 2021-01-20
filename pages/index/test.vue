<template>
	<view style="padding: 10rpx;">
		<u-search v-model="value" @change="change" @custom="custom" @search="search" :shape="shape" :clearabled="clearabled"
		:show-action="showAction" :input-align="inputAlign" @clear="clear"></u-search>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value: '',
				shape: 'round',
				clearabled: true,
				showAction: true,
				inputAlign: 'left'
				
				
			}
		},
		methods: {
			GoSearch(){
				uni.navigateTo({
					url: 'searchResult?searchText=' + this.searchText 
					
				});
				},
				change(value) {
					// 搜索框内容变化时，会触发此事件，value值为输入框的内容
					//console.log(value);
				},
				custom(value) {
					//console.log(value);
					this.$u.toast('输入值为：' + value)
				},
				search(value) {
					this.$refs.uToast.show({
						title: '搜索内容为：' + value,
						type: 'success'
					})
				},
				clear() {
					// console.log(this.value);
				}
			
		}
	}
</script>

<style>

</style>
