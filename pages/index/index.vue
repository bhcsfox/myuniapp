<template>
	<view class="content">
		<view>
			<view class="headerNavigationbar rowCenBet borderBox">
				<view class="leftContent rowCen">
					<view class="backIcon rowCenSta" @click="backUrl()">
						<image src="@/static/return.png" mode=""></image>
					</view>
					<view class="search-container rowCenBet borderBox">
						<input class="searchInput" type="text" @input='searchInput' @confirm="GoSearch()" v-model="searchText"
						 placeholder="输入商品或粘贴宝贝标题搜索" placeholder-class='searchplaceHolder' />
						<view class="rightIcon rowCenBet" v-if="searchText">
							<view class="searchicon iconfont" @click="cleanSearch()">
								&#xe641;
							</view>
						</view>
					</view>
				</view>
				<view class="searchbtn rowCenEnd" @click="GoSearch()">
					<view>搜索</view>
					
				</view>
			</view>
		</view>
		
<!-- 		
		<view class="">
			<view class="" v-for="item in indexlist" style="display: flex;">
				<image :src="item.mainPic" style="width: 260rpx;height: 260rpx;"></image>
				<view class="">{{item.dtitle}}</view>
				
			</view>
		</view> -->
		<goodsInfo v-for="item in indexlist" :item="item">
			
		</goodsInfo>
		
		
	</view>
</template>

<script>
	import goodsInfo from "component/goodsInfo.vue"
	export default {
		components:{
			goodsInfo
		},
		data() {
			
			return {
				title: 'Hello',
				searchText:'',
				indexlist:[],
				pageId:1
		
			}
		},
		onPullDownRefresh() {
			this.getList();
			setTimeout(function () {
			   uni.stopPullDownRefresh();  //停止下拉刷新动画
			        }, 1500);
		},
		onLoad() {
			this.getList();

		},
		onReachBottom() {
			//上拉加载			
		this.getList();
		
		},
		methods: {
			cleanSearch() {
				this.searchText = ''
			},
			getList(){
				uni.request({
					header: {'Content-Type': 'application/x-www-form-urlencoded'}, 
					url:'http://www.daxiajiaocheng.com/indexlist.php',
					method:'POST',
					data:{
						pageId:this.pageId
					},
					success: (res) => {
						console.log(res);
						this.pageId=this.pageId+1;
					
						res.data.data.forEach(d=>{
							d.dtitle=d.dtitle.replace("【","");
							d.dtitle=d.dtitle.replace("】","");
							d.monthSales=d.monthSales>10000?(d.monthSales/10000).toFixed(1)+'万':d.monthSales;
						});
						this.indexlist=this.indexlist.concat(res.data.data);                                                                 
						
					}
					
				})
				
				
			},
			GoSearch(){
				uni.navigateTo({
					url: 'search'
				})
				},
				searchInput(){
					
				}

		}
	}
</script>

<style lang="scss">
	
	.backIcon {
		width: 40rpx;
		height: 32rpx;
		z-index: 1;
	
		image {
			width: 17rpx;
			height: 32rpx;
		}
		}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		
	}


</style>
