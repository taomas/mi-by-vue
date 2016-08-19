<template>
	<div class="around-container">
		<goods-top
			:top-title="topTitle"
			:subs="subs"></goods-top>
		<div class="goods-content clearfix">
			<goods-left
				:left-goods="leftGoods"
			></goods-left>
			<goods-right
				:hot-goods="hotGoods"
			></goods-right>
		</div>
	</div>
</template>

<script>
import GoodsTop from './common/GoodsTop'
import GoodsLeft from './common/GoodsLeft'
import GoodsRight from './common/GoodsRight'
export default {
	data () {
		return {
			topTitle: '周边',
			subs: [
				{name: '热门', key: 'hot'},
				{name: '服装', key: 'clothes'},
				{name: '米兔', key: 'rabbit'},
				{name: '生活周边', key: 'around'},
				{name: '箱包', key: 'bags'}
			],
			leftGoods: [
				{imgUrl: 'http://i3.mifile.cn/a4/ff2a2f99-2c69-4472-acc1-e16322ee79ba'},
				{imgUrl: 'http://i3.mifile.cn/a4/c2b64ac9-0b29-4158-a4ab-66aca1720916'}
			],
			hotGoods: [
				{imgUrl: 'http://i3.mifile.cn/a4/T1IDC_B_Kv1RXrhCrK.jpg', 'title': '小米V领短袖T恤 男款', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/e8f5a80c-7f57-4f7b-97fc-c446059d2381', 'title': '小米短袖T恤 水管工米兔', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/d3897b3a-59b4-4cdb-a726-f318f0ee44b6', 'title': '小米短袖T恤 新国货', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/23c8122a-3bf4-4675-abb2-aca349aa1923', 'title': '小米V领短袖T恤 女款', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/6ddc1df6-ce8e-4cb5-a26a-b5ef80f1adf7', 'title': '小米经典商务双肩包', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i1.mifile.cn/a1/pms_1468310472.00391359!220x220.jpg', 'title': '米家随身电蚊香', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/5a28d943-ef5d-4920-a89a-7f1bce6c5b35', 'title': '米家LED随身灯 增强版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i3.mifile.cn/a4/T1yo_gBm_v1RXrhCrK.jpg', 'title': '金属鼠标垫 小号', price: '79'}
			]
		}
	},
	components: {
		'goods-top': GoodsTop,
		'goods-left': GoodsLeft,
		'goods-right': GoodsRight
	}
}
</script>

<style>
.around-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
.goods-content {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
</style>
