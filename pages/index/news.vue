<!-- 文章资讯 -->
<template>
	<view>
		<cu-custom bgColor="bg-gradual-blue" :isBack="true">
			<!-- <block slot="backText">返回</block> -->
			<block slot="content">文章资讯</block>
		</cu-custom>

		<scroll-view scroll-x class="bg-white nav" scroll-with-animation :scroll-left="scrollLeft">
			<view class="cu-item" :class="index == TabCur?'text-blue cur':''" v-for="(item,index) in navTop" :key="index" @tap="tabSelect"
			 :data-id="index">
				{{item.title}}
			</view>
		</scroll-view>
		
		<view class="cu-card article no-card">
			<view class="cu-item shadow borderBottom" @click="goNews">
				<view class="title"><view class="text-cut">茂名市红十字会开展“好心茂名 • 救心大行动”网络公益募捐</view></view>
				<view class="content">
					<image src="https://nwzimg.wezhan.cn/contents/sitefiles2040/10204453/images/20330649.png"
					 mode="scaleToFill"></image>
					<view class="desc">
						<view class="text-content">根据临床统计，我国先天性心脏病的发病率占出生婴儿的0.4%～1%，每年全国新增先天性心脏病患者15～20万。茂名是全国人口大市，每年新增先天性心脏病患儿约500～600人。小儿先天性心脏病手术的最佳治疗时机是在学龄前期，90%以上的先天性心脏病可以通过手术治愈，但大部分困难家庭因无法支付几万乃至十几万元的医疗费用而错过最佳治疗时机，半数以上患儿在病情恶化中无奈地挣扎和等待，甚至死亡。先天性心脏病现已成为导致新生儿及婴幼儿死亡的一大杀手，给家庭及社会造成了严重的经济及精神负担。

为帮助茂名困难家庭先天性心脏病患者早日得到有效的救治，茂名市红十字会、茂名日报社等单位联合成立 “好心茂名·救心大行动”公益项目，为实现我市困难家庭先天性心脏病儿童实施免费手术救治的目标。</view>
						<view class="margin-top-xs">
							<view class="text-gray light sm round fl">2021年11月01日</view>
							<view class="text-gray light sm round fr">
								<text class="text-gray cuIcon-appreciate" style="font-size: 34rpx;"></text>
								<text>11</text>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		

	</view>
</template>

<script>
	export default {
		data() {
			return {
				TabCur: 0,
				scrollLeft: 0,
				navTop:[
					{
						id: 1,
						title: '机关活动'
					},
					{
						id: 2,
						title: '基层活动'
					},
					{
						id:3,
						title: '会员活动'
					},
					{
						id:4,
						title: '防灾救灾'
					},
					{
						id:5,
						title: '课程活动'
					}
				]
			};
		},
		methods: {
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			},
			goNews(){
				uni.navigateTo({
					url: ''
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.borderBottom{
		border-bottom: 1px solid #f2f2f2;
	}
</style>
