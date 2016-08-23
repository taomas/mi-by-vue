<template>
	<div class="top-banner clearfix">
		<div class="site-category"
			@mouseleave="evtSideLeave">
			<div class="top-side-left">
				<ul class="side-left">
					<li class="side-item"
						@mouseenter="evtSideEnter(item.type)"
						v-for="item in sideItems">
						{{item.content}}
					</li>
				</ul>
			</div>
			<div class="site-category-detail"
				v-show="goodsStatus">
				<ul class="category-items" v-for="goods in filterCurrGoods">
					<li class="category-goods" v-for="item in goods">
						<img :src="item.imgUrl" alt="" />
						<div class="text-name">
							{{item.name}}
						</div>
						<div
							v-show="item.buyStatus"
							class="btn-buy">
							选购
						</div>
					</li>
				</ul>
			</div>
		</div>
		<slide :banners="banners"></slide>
	</div>
</template>

<script>
import slide from './common/Slide.vue'
export default {
	data () {
		return {
			currGoods: [],
			goodsStatus: false,
			sideItems: [
				{type: 'phones', content: '手机 电话卡'},
				{type: 'computer', content: '笔记本 平板'},
				{type: 'box', content: '电视 盒子'},
				{type: 'router', content: '路由器 智能硬件'},
				{type: 'power', content: '移动电源 电池 插线板'},
				{type: 'headset', content: '耳机 音响'},
				{type: 'foil', content: '保护套 贴膜'},
				{type: 'line', content: '线材 支架 存储卡'},
				{type: 'bags', content: '箱包 服饰'},
				{type: 'rabbit', content: '兔米 生活周边'}],
			banners: [
				{imgUrl: 'http://i3.mifile.cn/a4/ef9c4e97-2971-495c-987d-bd3f3b1b7b58', sourceUrl: ''},
				{imgUrl: 'http://i3.mifile.cn/a4/3c788170-183e-4f26-b00b-6ef1b743906c', sourceUrl: ''},
				{imgUrl: 'http://i3.mifile.cn/a4/67c4e203-f46b-4e58-8da2-859d69c313fb', sourceUrl: ''},
				{imgUrl: 'http://i3.mifile.cn/a4/709b3551-c643-498c-8dcd-2572baa56bd6', sourceUrl: ''},
				{imgUrl: 'http://i3.mifile.cn/a4/dab07ffc-8853-4b2f-9a90-da297c98d6d3', sourceUrl: ''}
			],
			phones: [
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '小米手机5', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/maxbar80.jpg?width=40&height=40', name: '小米Max', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/note3.jpg?width=40&height=40', name: '小米Note3', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/hm3s80x80.jpg?width=40&height=40', name: '红米手机3S', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hongmi3.jpg?width=40&height=40', name: '红米Pro', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '红米手机3', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/3X80.jpg?width=40&height=40', name: '红米手机3X', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/heyue.jpg?width=40&height=40', name: '合约机', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/compare.jpg?width=40&height=40', name: '对比手机', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/mimobile.jpg?width=40&height=40', name: '小米移动 电话卡', buyStatus: false}
			],
			computer: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: true},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			box: [
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/4380side.jpg?width=40&height=40', name: '小米电视 43英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/mitv3s48.jpg?width=40&height=40', name: '小米电视 48英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv3-55.jpg?width=40&height=40', name: '小米电视 55英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv60.jpg?width=40&height=40', name: '小米电视 60英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/6580side.jpg?width=40&height=40', name: '小米电视 65英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv70.png?width=40&height=40', name: '小米电视 70英寸', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tvzj.jpg?width=40&height=40', name: '小米电视主机', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezizengqiangban80side.jpg?width=40&height=40', name: '小米盒子3 增强版', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezis.jpg?width=40&height=40', name: '小米盒子3', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezimini.jpg?width=40&height=40', name: '小米盒子 mini', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/diyinpao.jpg?width=40&height=40', name: '小米低音炮', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/shb.jpg?width=40&height=40', name: '蓝牙手柄', buyStatus: false}
			],
			router: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			power: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			headset: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			foil: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			line: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			bags: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			rabbit: [
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			]

		}
	},
	ready () {
	},
	computed: {
		filterCurrGoods: function () {
			let filterGoods = [[], [], [], [], []]
			this.currGoods.forEach(function (item, index) {
				let goodsIndex = Math.floor(index / 6)
				filterGoods[goodsIndex].push(item)
			})
			console.log(filterGoods)
			return filterGoods
		}
	},
	methods: {
		evtSideEnter (currType) {
			this.currGoods = this[currType]
			this.goodsStatus = true
		},
		evtSideLeave () {
			this.goodsStatus = false
		}
	},
	components: {
		slide
	}
}
</script>

<style scoped>
.top-banner {
	position: relative;
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
.site-category {
	position: absolute;
	left: 0;
	top: 0;
	width: 235px;
	height: auto;
	padding: 20px 0;
	background: rgba(0, 0, 0, 0.3);
	z-index: 10;
}

.side-left {
	margin: 0;
	padding: 0;
	width: 235px;
	height: 420px;
	list-style: none;
	.side-item {
		width: 100%;
		height: 42px;
		line-height: 42px;
		font-size: 14px;
		color: #fff;
		text-align: center;
		cursor: pointer;
		&:hover {
			background: #ff6700;
		}
	}
}

.site-category-detail {
	position: absolute;
	display: flex;
	flex-flow: row nowrap;
	justify-content: flex-start;
	left: 235px;
	top: 0;
	z-index: 10;
	.category-items {
		width: auto;
		height: 460px;
		margin: 0;
		padding: 0;
		list-style: none;
		background: #fff;
	}
	.category-goods {
		display: flex;
		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: center;
		width: 265px;
		height: 76.6px;
		padding: 0 26px 0 26px;
		box-sizing: border-box;
		background: #fff;
		cursor: pointer;
		.text-name {
			padding-left: 20px;
			font-size: 14px;
			width: 120px;
		}
		.btn-buy {
			width: 58px;
			height: 22px;
			line-height: 24px;
			font-size: 12px;
			text-align: center;
			color: #ff6700;
			border: 1px solid #ff6700;
			&:hover {
				color: #fff;
				background: #ff6700;
			}
		}
	}
}
</style>
