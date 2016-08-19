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
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米小钢炮', price: '79'}
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
