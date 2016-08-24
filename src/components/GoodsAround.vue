<template>
	<div class="around-container">
		<div class="goods-top clearfix">
			<h3 class="top-title">周边</h3>
			<ul class="top-sub">
				<li v-for="sub in subs"
					:class="{'active': topSubStatus === sub.key}"
					@mouseenter="topSubEnter(sub.key)">{{sub.name}}</li>
			</ul>
		</div>
		<div class="goods-content clearfix">
			<goods-left
				:left-goods="leftGoods"
			></goods-left>
			<goods-right
				:curr-goods="currGoods"
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
			currGoods: [],
			topSubStatus: 'hot',
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
			hot: [
				{sourceUrl: '//item.mi.com/1151400027.html', imgUrl: 'http://i3.mifile.cn/a4/T1IDC_B_Kv1RXrhCrK.jpg', title: '小米V领短袖T恤 男款', price: '29', oldPrice: '39', heat: '1.6万',
				reviewDesc: '穿着这衣服，真是舒服，就想抱着女朋友的感觉一样 ', reviewAuthor: '574081459', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000019.html', imgUrl: 'http://i3.mifile.cn/a4/e8f5a80c-7f57-4f7b-97fc-c446059d2381', title: '小米短袖T恤 水管工米兔', price: '29', oldPrice: '39', heat: '3567',
				reviewDesc: '感觉非常不错，特别是这上边的图案，萌萌哒！', reviewAuthor: '478670150', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1162200008.html', imgUrl: 'http://i3.mifile.cn/a4/d3897b3a-59b4-4cdb-a726-f318f0ee44b6', title: '小米短袖T恤 新国货', price: '29', oldPrice: '39', heat: '476',
				reviewDesc: '货品收到了！这个印花太耀眼了。', reviewAuthor: '乌之江下面', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000025.html', imgUrl: 'http://i3.mifile.cn/a4/23c8122a-3bf4-4675-abb2-aca349aa1923', title: '小米V领短袖T恤 女款', price: '29', oldPrice: '39', heat: '3075',
				reviewDesc: '好穿级了，纯棉，手感不错，性价比高', reviewAuthor: '狗都爱吃肉', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161100002.html', imgUrl: 'http://i3.mifile.cn/a4/6ddc1df6-ce8e-4cb5-a26a-b5ef80f1adf7', title: '小米经典商务双肩包', price: '99', oldPrice: '39', heat: '4426',
				reviewDesc: '非常好的包包，做工精细，走线整齐，连拉链都很精致。9...', reviewAuthor: '933771817', reviewStatus: true},
				{sourceUrl: '//www.mi.com/mimosdge/', imgUrl: 'http://i1.mifile.cn/a1/pms_1468310472.00391359!220x220.jpg ', title: '米家随身电蚊香', price: '29', oldPrice: '39', heat: '1927',
				reviewDesc: '这个真不错！我用超威蚊香片插放很容易！它使用的标准尺...', reviewAuthor: 'LGH863117', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1162800009.html', imgUrl: 'http://i3.mifile.cn/a4/5a28d943-ef5d-4920-a89a-7f1bce6c5b35', title: '米家LED随身灯 增强版', price: '19.9', oldPrice: '39', heat: '2261',
				reviewDesc: '很好用！特别是五挡开关灯，好用！方便！', reviewAuthor: '86505510', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1144600004.html', imgUrl: 'http://i3.mifile.cn/a4/T1yo_gBm_v1RXrhCrK.jpg', title: '金属鼠标垫 小号', price: '49'}
			],
			clothes: [
				{sourceUrl: '//item.mi.com/1161000022.html', imgUrl: '//i3.mifile.cn/a4/T1i.YjBbWT1RXrhCrK.jpg', title: '小米短袖T恤 情侣米兔 女款', price: '29', oldPrice: '39', heat: '1558',
				reviewDesc: '衣服质量不错，样式也不错 ', reviewAuthor: '小紅帽0809', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000027.html', imgUrl: '//i3.mifile.cn/a4/a2973973-b7f1-4431-988b-449c0d068419', title: '小米V领短袖T恤 女款', price: '29', oldPrice: '39', heat: '3075',
				reviewDesc: '好穿级了，纯棉，手感不错，性价比高', reviewAuthor: '狗都爱吃肉', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000018.html', imgUrl: '//i3.mifile.cn/a4/T1ReJ_B_Kv1RXrhCrK.jpg', title: '小米短袖T恤 小熊米兔', price: '29', oldPrice: '39', heat: '4512',
				reviewDesc: '女朋友说了，衣服不错就是人丑了点。', reviewAuthor: 'Mi_940790865', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000020.html', imgUrl: '//i3.mifile.cn/a4/357bebdd-6e77-4c43-a33c-b8287caace2e', title: '小米短袖T恤 水管工米兔', price: '29', oldPrice: '39', heat: '3567',
				reviewDesc: '感觉非常不错，特别是这上边的图案，萌萌哒！', reviewAuthor: '478670150', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000032.html', imgUrl: '//i3.mifile.cn/a4/T1GXYgBgJv1RXrhCrK.jpg', title: '小米短袖POLO衫 女款', price: '59', oldPrice: '39', heat: '1023',
				reviewDesc: '颜色很正，质地好，我继续支持小米！', reviewAuthor: 'Mi_657996558', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000021.html', imgUrl: '//i3.mifile.cn/a4/T1MIC_BTLv1RXrhCrK.jpg', title: '小米短袖T恤 轻松米兔', price: '29', oldPrice: '39', heat: '4629',
				reviewDesc: '便宜好货，胜过nike，做工精细，新国货 ，小米加油！', reviewAuthor: '蓝海苑', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000035.html', imgUrl: '//i3.mifile.cn/a4/T1m3CgBXJv1RXrhCrK.jpg', title: '小米短袖T恤 摇滚星球', price: '29', oldPrice: '39', heat: '2622',
				reviewDesc: '纯棉的穿的很舒服！样式好看！', reviewAuthor: '434388030', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161000034.html', imgUrl: '//i3.mifile.cn/a4/T1L_D_B7Jv1RXrhCrK.jpg', title: '小米短袖T恤  五彩环', price: '29'}
			],
			rabbit: [
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: ''}
			],
			around: [
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: ''}
			],
			bags: [
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: '', oldPrice: '', heat: '',
				reviewDesc: '', reviewAuthor: '', reviewStatus: true},
				{sourceUrl: '', imgUrl: '', title: '', price: ''}
			]
		}
	},
	ready () {
		this.currGoods = this.hot
	},
	methods: {
		topSubEnter (key) {
			this.topSubStatus = key
			this.currGoods = this[key]
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
.goods-top {
	width: 100%;
	height: 58px;
	.top-title {
		float: left;
		margin: 0;
		font-size: 22px;
		font-weight: 200;
		line-height: 58px;
		color: #333;
	}
	.top-sub {
		float: right;
		display: flex;
		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: center;
		font-size: 16px;
		margin-top: 16px;
		color: #424242;
		li {
			width: auto;
			height: 24px;
			line-height: 24px;
			margin-left: 30px;
			cursor: pointer;
			border-bottom: 2px solid #f5f5f5;
			&.active {
				color: #ff6700;
				border-bottom: 2px solid #ff6700;
			}
		}
	}
}
</style>
