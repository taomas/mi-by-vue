<template>
	<div class="top-banner clearfix">
		<div class="site-category"
			@mouseleave="evtSideLeave">
			<div class="top-side-left">
				<ul class="side-left">
					<li class="side-item"
						@mouseenter="evtSideEnter"
						v-for="item in sideItems">
						{{item}}
					</li>
				</ul>
			</div>
			<div class="site-category-detail"
				v-show="goodsStatus">
				<ul class="category-items" v-for="goods in phones">
					<li class="category-goods" v-for="item in goods">
						<img :src="item.sourcePath" alt="" />
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
			goodsStatus: false,
			sideItems: ['手机 电话卡', '笔记本 平板', '电视 盒子', '路由器 智能硬件', '移动电源 电池 插线板', '耳机 音响', '保护套 贴膜', '线材 支架 存储卡', '箱包 服饰', '兔米 生活周边'],
			banners: [
				{sourcePath: 'http://i3.mifile.cn/a4/ef9c4e97-2971-495c-987d-bd3f3b1b7b58'},
				{sourcePath: 'http://i3.mifile.cn/a4/3c788170-183e-4f26-b00b-6ef1b743906c'},
				{sourcePath: 'http://i3.mifile.cn/a4/67c4e203-f46b-4e58-8da2-859d69c313fb'},
				{sourcePath: 'http://i3.mifile.cn/a4/709b3551-c643-498c-8dcd-2572baa56bd6'},
				{sourcePath: 'http://i3.mifile.cn/a4/dab07ffc-8853-4b2f-9a90-da297c98d6d3'}
			],
			phones: [
				[
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '小米手机5', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/maxbar80.jpg?width=40&height=40', name: '小米Max', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/note3.jpg?width=40&height=40', name: '小米Note3', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/g/2015/video/hm3s80x80.jpg?width=40&height=40', name: '红米手机3S', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hongmi3.jpg?width=40&height=40', name: '红米Pro', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '红米手机3', buyStatus: true}
				],
				[
					{sourcePath: 'http://c1.mifile.cn/f/i/g/2015/video/3X80.jpg?width=40&height=40', name: '红米手机3X', buyStatus: true},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/heyue.jpg?width=40&height=40', name: '合约机', buyStatus: false},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/compare.jpg?width=40&height=40', name: '对比手机', buyStatus: false},
					{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/mimobile.jpg?width=40&height=40', name: '小米移动 电话卡', buyStatus: false}
				]
			],
			computer: [
				{sourcePath: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: true},
				{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: true},
				{sourcePath: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: true},
				{sourcePath: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: true}
			]
		}
	},
	computed: {
		currGoods: function () {
		}
	},
	methods: {
		evtSideEnter () {
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
		padding: 0 10px 0 26px;
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
