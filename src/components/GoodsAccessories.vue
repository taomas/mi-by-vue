<template>
	<div class="around-container">
		<div class="goods-top clearfix">
			<h3 class="top-title">配件</h3>
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
			topTitle: '配件',
			subs: [
				{name: '热门', key: 'hot'},
				{name: '保护套', key: 'protect'},
				{name: '贴膜', key: 'fiol'},
				{name: '其它配件', key: 'other'}
			],
			currGoods: [],
			topSubStatus: 'hot',
			leftGoods: [
				{sourceUrl: '//list.mi.com/30', imgUrl: 'http://i3.mifile.cn/a4/aa163c95-2890-4227-967c-a05ccec6c4a9'},
				{sourceUrl: '//www.mi.com/powerstrip/', imgUrl: 'http://i3.mifile.cn/a4/363032e6-b043-4854-a8cc-8909df918f02'}
			],
			hot: [
				{sourceUrl: '//item.mi.com/1153300034.html', imgUrl: '//i2.mifile.cn/a1/T1COAjB7WT1RXrhCrK.jpg?width=150&height=150', title: '指环式防滑手机支架', price: '12.5', heat: '8087',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1151500039.html', imgUrl: '//i2.mifile.cn/a1/T1_SDgB4KT1RXrhCrK.jpg?width=150&height=150', title: '小米自拍杆', price: '49', heat: '7.6万',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1154900023.html', imgUrl: '//i2.mifile.cn/a1/T1l9WjBTbT1RXrhCrK.jpg?width=150&height=150', title: '青米USB快速充电数据线', price: '14.9', heat: '1.4万',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1135200036.html', imgUrl: '//i2.mifile.cn/a1/T1zL_vByCT1RXrhCrK.jpg?width=150&height=150', title: '小米随身WIFI', price: '19.9', heat: '29.9万',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1154900055.html', imgUrl: '//i2.mifile.cn/a1/T1AmJgBsKT1RXrhCrK.jpg?width=150&height=150', title: '苹果Lightning to USB数据线', price: '39', heat: '1.6万',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1162800007.html', imgUrl: '//i2.mifile.cn/a1/pms_1468287589.40786199.jpg?width=150&height=150', title: '米家随身风扇', price: '19.9', heat: '4434',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1144900003.html', imgUrl: '//i2.mifile.cn/a1/T1_8YvBKJT1RXrhCrK.jpg?width=150&height=150', title: '功夫米兔手机支架', price: '19', heat: '1.9万',
				reviewDesc: '', reviewAuthor: '', reviewStatus: false},
				{moreUrl: '//list.mi.com/pjrm', sourceUrl: '//item.mi.com/1154100024.html', imgUrl: '//i2.mifile.cn/a1/T1Zp__B5Ev1RXrhCrK.jpg?width=80&height=80', title: 'ZMI无限拓展数据线 120cm', price: '29'}
			],
			protect: [
				{sourceUrl: '//item.mi.com/1160800014.html', imgUrl: '//i1.mifile.cn/a1/T12AWgB5Vv1RXrhCrK!220x220.jpg', title: '小米手机5 智能翻盖保护套', price: '49', heat: '1.5万',
				reviewDesc: '很不错，很好用。已推荐朋友使用。', reviewAuthor: '舊時書生', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161600009.html', imgUrl: '//i1.mifile.cn/a1/T1XVWjBCYv1RXrhCrK!220x220.jpg', title: '小米Max 智能显示保护套', price: '59', heat: '4179',
				reviewDesc: '这个唤醒保护套功能还真不错~~给家人买的，等米ＭＡＸ...', reviewAuthor: '姮Fiona.mo', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1162500028.html', imgUrl: '//i1.mifile.cn/a1/pms_1469787847.44636521!220x220.jpg', title: '红米Pro 智能显示保护套', price: '49', heat: '190',
				reviewDesc: '又是一款精品，喜欢，小米值得拥有！', reviewAuthor: '174473315', reviewStatus: true, discountType: 'new', discount: '新品'},
				{sourceUrl: '//item.mi.com/1161200045.html', imgUrl: '//i1.mifile.cn/a1/T18sWvBTxv1RXrhCrK!220x220.jpg', title: '红米3高配版 炫彩翻盖保护套', price: '2939', heat: '4775',
				reviewDesc: '这个我感觉是我买的性价比最好的手机外套了', reviewAuthor: '煎饼', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1154800016.html', imgUrl: '//i1.mifile.cn/a1/T10Eb_BmAv1RXrhCrK!220x220.jpg', title: '红米Note3 炫彩翻页保护套', price: '39', heat: '2.2万',
				reviewDesc: '大小合适，特别好，质量和颜色都非常棒', reviewAuthor: '142010366', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1160100013.html', imgUrl: '//i3.mifile.cn/a4/T1WLx_BgVv1RXrhCrK.jpg', title: '红米3标准版 炫彩翻盖保护套', price: '29', heat: '6908',
				reviewDesc: '很好的手机保护套，质量ok ', reviewAuthor: 'binarystar1989', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1142900047.html', imgUrl: '//i1.mifile.cn/a1/T11eEvBmYT1RXrhCrK!220x220.jpg', title: '小米手机4 智能唤醒翻盖保护套', price: '1549', heat: '11.5万',
				reviewDesc: '小米4保护套一下买了两个，玫红和柠檬绿，生活如此多娇！', reviewAuthor: '゛ロ隹╲ー', reviewStatus: true, oldPrice: '49', discountType: 'discount', discount: '享4折'},
				{moreUrl: '//list.mi.com/7', sourceUrl: '//item.mi.com/1155100020.html', imgUrl: '//i1.mifile.cn/a1/T1QKJ_BvLv1RXrhCrK!220x220.jpg', title: '平板2保护套', price: '69'}
			],
			fiol: [
				{sourceUrl: '//item.mi.com/1160800004.html', imgUrl: '//i3.mifile.cn/a4/T1cVLjBX_v1RXrhCrK.jpg', title: '小米手机5 极薄防蓝光贴膜', price: '49', heat: '6324',
				reviewDesc: '我用过最好的产品！性能彪悍，工艺精湛，美美美', reviewAuthor: '川四大', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161600029.html', imgUrl: '//i1.mifile.cn/a1/T1y7JQBbCT1RXrhCrK!220x220.jpg', title: '小米Max 标准高透贴膜 ', price: '19', heat: '6384',
				reviewDesc: '说是高透就是高透，贴上贴膜，带领领略高透滴全世界～～ ', reviewAuthor: '148800310', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154800022.html', imgUrl: '//i1.mifile.cn/a1/T1SSJ_B4E_1RXrhCrK!220x220.jpg', title: '小米平板2 标准高透贴膜', price: '29', heat: '1290',
				reviewDesc: '挺好用的，发货也快，清晰！', reviewAuthor: '卖蘑菇的小和尚', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154800026.html', imgUrl: '//i3.mifile.cn/a4/T1qdEgBKKv1RXrhCrK.jpg', title: '红米Note3 钢化玻璃膜', price: '19', heat: '3.6万',
				reviewDesc: '钢化膜表面很光滑，和手机屏幕玻璃一样，很好', reviewAuthor: 'Pioneer77', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1160100021.html', imgUrl: '//i1.mifile.cn/a1/T1g7J_BsLv1RXrhCrK!220x220.jpg', title: '红米手机3 钢化玻璃膜', price: '9.9', heat: '7582',
				reviewDesc: '很好，容易贴上，触感不错', reviewAuthor: '247292055', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1160800006.html', imgUrl: '//i1.mifile.cn/a1/T1t2K_B4L_1RXrhCrK!220x220.jpg', title: '小米手机5 钢化玻璃贴膜', price: '29', heat: '2.9万',
				reviewDesc: '膜的质量很好，不粘指纹，', reviewAuthor: ' 乱世风凌乱', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1162500021.html', imgUrl: '//i1.mifile.cn/a1/pms_1469787992.44385373!220x220.jpg', title: '红米Pro 标准高透贴膜', price: '19', heat: '437',
				reviewDesc: '很好，物流非常快，还有贴膜的方法，并且附赠两张贴膜放...', reviewAuthor: '1123887372', reviewStatus: true},
				{moreUrl: '//list.mi.com/9', sourceUrl: '//item.mi.com/1160800005.html', imgUrl: '//i1.mifile.cn/a1/T1keE_BsJv1RXrhCrK!220x220.jpg ', title: '小米手机5 标准高透贴膜', price: '19'}
			],
			other: [
				{sourceUrl: '//item.mi.com/1152500016.html', imgUrl: '//i1.mifile.cn/a1/T1xXxQBCVT1RXrhCrK!220x220.jpg', title: '小蚁蓝牙遥控器', price: '39', heat: '2778',
				reviewDesc: '宝贝挺好的，开始联不上，把相机固件升级了才能联上，非...', reviewAuthor: '老叶8', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1153300036.html', imgUrl: '//i1.mifile.cn/a1/T1j_D_BQWT1RXrhCrK!220x220.jpg', title: '指环式防滑手机支架', price: '12.5', heat: '8087',
				reviewDesc: '很好的设计，太实用了，更方便单手操作了，不用担心手机...', reviewAuthor: '疯流涕淌王', reviewStatus: true},
				{sourceUrl: '//www.mi.com/shb/', imgUrl: '//i1.mifile.cn/a1/T1WTEvBmKT1RXrhCrK!220x220.jpg', title: '小米蓝牙手柄', price: '99', heat: '2.7万',
				reviewDesc: '手感超好，联上小米电视玩游戏超爽，就是电视端游戏有待...', reviewAuthor: '陈峪汀', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154200029.html', imgUrl: '//i1.mifile.cn/a1/T11oW_B4dv1RXrhCrK!220x220.jpg', title: '蓝牙语音体感遥控器', price: '99', heat: '2387',
				reviewDesc: '好使～方便～语音更好！呵呵，支持小米！！！', reviewAuthor: '静一licf', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1153900018.html', imgUrl: '//i1.mifile.cn/a1/T1juCgBgxT1RXrhCrK!220x220.jpg', title: '手机USB Type-C数据线', price: '39', heat: '1.4万',
				reviewDesc: '很好用的数据线，充电传输都很好', reviewAuthor: '103898410', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1150500009.html', imgUrl: '//i1.mifile.cn/a1/T13y_vBgJT1RXrhCrK!220x220.jpg', title: '小米千兆网线', price: '14.9', heat: '3万',
				reviewDesc: '早点出多好啊！盒子不卡了！电脑下载不卡顿了！神药啊！...', reviewAuthor: '水云间789', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154100024.html', imgUrl: '//i1.mifile.cn/a1/T1Zp__B5Ev1RXrhCrK!220x220.jpg', title: 'ZMI无限拓展数据线', price: '29', heat: '4719',
				reviewDesc: '长度够用，牢固，质量不错', reviewAuthor: '396139651', reviewStatus: true},
				{moreUrl: '//list.mi.com/others', sourceUrl: '//item.mi.com/1154900025.html', imgUrl: '//i1.mifile.cn/a1/T1_7KgB4Jv1RXrhCrK!220x220.jpg', title: '青米USB快速充电数据线', price: '24.9'}
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
