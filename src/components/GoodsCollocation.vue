<template>
	<div class="around-container">
		<div class="goods-top clearfix">
			<h3 class="top-title">搭配</h3>
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
			topTitle: '搭配',
			subs: [
				{name: '热门', key: 'hotGoods'},
				{name: '耳机音响', key: 'headset'},
				{name: '电源', key: 'power'},
				{name: '电池存储卡', key: 'battery'}
			],
			topSubStatus: 'hotGoods',
			currGoods: [],
			leftGoods: [
				{sourceUrl: '//www.mi.com/dianyuan10000/', imgUrl: 'http://i3.mifile.cn/a4/54581b2c-f88d-4415-9754-af83116346bd'},
				{sourceUrl: '//www.mi.com/capsuleearphone/', imgUrl: 'http://i3.mifile.cn/a4/f7da6234-7159-414a-a2ea-8832af89b4f1'}
			],
			hotGoods: [
				{sourceUrl: '/item.mi.com/1151900011.html', imgUrl: '//i2.mifile.cn/a1/T12HJvByEv1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh',
					price: '79', heat: '19.2万', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1160900029.html', imgUrl: '//i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版',
					price: '149', heat: '2万', reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1161200010.html', imgUrl: '//i2.mifile.cn/a1/T1ycK_BjYv1RXrhCrK.jpg?width=150&height=150', 'title': '小米圈铁耳机',
					price: '99', heat: '1.4万', reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1151400001.html', imgUrl: '//i2.mifile.cn/a1/pms_1463579883.27084326.jpg?width=150&height=150', 'title': '小米插线板',
					price: '49', heat: '24.7万', reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1152400013.html', imgUrl: '//i2.mifile.cn/a1/T190DvB4dv1RXrhCrK.jpg?width=150&height=150', 'title': '小米蓝牙耳机',
					price: '79', oldPrice: '8.8', heat: '2万', reviewDesc: '小米的产品值得信赖，用了一段时间，无论是听歌，打电话...', reviewAuthor: '气功流', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161200004.html', imgUrl: '//i2.mifile.cn/a1/T1WxYvB_xv1RXrhCrK.jpg?width=150&height=150', 'title': '小米活塞耳机 基础版',
					price: '29', heat: '5.5万', reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: false},
				{sourceUrl: '//item.mi.com/1154300036.html', imgUrl: '//i2.mifile.cn/a1/T1F5K_BjVv1RXrhCrK.jpg?width=150&height=150', 'title': '小米小钢炮蓝牙音箱2',
					price: '129', heat: '1.2万', reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: false},
				{moreUrl: '//list.mi.com/dapei', sourceUrl: '//item.mi.com/1161800005.html', imgUrl: '//i2.mifile.cn/a1/T15hZ_BsDv1RXrhCrK.jpg?width=80&height=80', 'title': '小米小钢炮蓝牙音箱 青春版 象牙白', price: '99'}
			],
			headset: [
				{sourceUrl: '//www.mi.com/huosai2/', imgUrl: '//i3.mifile.cn/a4/T1..W_Bvxv1RXrhCrK.jpg', 'title': '小米活塞耳机 基础版',
					price: '29', heat: '5.4万', reviewDesc: '音质非常的好，很震撼！！美美美！', reviewAuthor: '米米小米aa', reviewStatus: true},
				{sourceUrl: '//www.mi.com/quantie/', imgUrl: '//i1.mifile.cn/a1/T1ycK_BjYv1RXrhCrK!220x220.jpg', 'title': '小米圈铁耳机',
					price: '99', heat: '1.3万', reviewDesc: '客服妹子实话说吧！永远支持国产，永远支持小米。这圈铁...', reviewAuthor: '894039435', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1161800009.html', imgUrl: '//i1.mifile.cn/a1/T1SkV_BCd_1RXrhCrK!220x220.jpg', 'title': '小米胶囊耳机',
					price: '69', heat: '1.1万', reviewDesc: '很小巧 像不喜欢戴活塞的人可以试试这种~很舒服包装还...', reviewAuthor: '鹤唳', reviewStatus: true},
				{sourceUrl: '//www.mi.com/bluetooth-headset/', imgUrl: '//i1.mifile.cn/a1/T190DvB4dv1RXrhCrK!220x220.jpg', 'title': '小米蓝牙耳机',
					price: '79', heat: '8.8万', reviewDesc: '东西不错，特别轻，以前买过别的蓝牙耳机，带几天就不带...', reviewAuthor: 'A@然', reviewStatus: true},
				{sourceUrl: '//www.mi.com/yinxiang/', imgUrl: '//i1.mifile.cn/a1/T1Tfd_BjAv1RXrhCrK!220x220.jpg', 'title': '小米小钢炮蓝牙音箱2',
					price: '129', heat: '1.1万', reviewDesc: '小米节礼券立减50，千值万值啊！物流很快，第二天就到...', reviewAuthor: '潇逸云', reviewStatus: true},
				{sourceUrl: '//www.mi.com/littleaudio/', imgUrl: '//i1.mifile.cn/a1/T1LqYgBCWv1RXrhCrK!220x220.jpg', 'title': '小米随身蓝牙音箱',
					price: '69', heat: '7513', reviewDesc: '小巧，便携，连接方便还有电量显示！总体很不错，可以挂...', reviewAuthor: '佰亊柒禧', reviewStatus: true},
				{sourceUrl: '//www.mi.com/pocketaudio/', imgUrl: '//i1.mifile.cn/a1/T1yf__BjAT1RXrhCrK!220x220.jpg', 'title': '小米蓝牙音箱',
					price: '199', oldPrice: '8.8', heat: '1.9万', reviewDesc: '还可以插内存卡，可以插线播放，音质很棒，如果体积大点...', reviewAuthor: '422979039', reviewStatus: true},
				{moreUrl: '//list.mi.com/17', sourceUrl: '//www.mi.com/speaker/', imgUrl: '//i1.mifile.cn/a1/T15hZ_BsDv1RXrhCrK!220x220.jpg', 'title': '小米小钢炮蓝牙音箱 青春版', price: '99'}
			],
			power: [
				{sourceUrl: '//www.mi.com/dianyuan5000/', imgUrl: '//i3.mifile.cn/a4/T1AcE_Bghv1RXrhCrK.jpg', 'title': '移动电源5000mAh',
					price: '49', heat: '8.7万', reviewDesc: '商品非常满意！本来是送给哥哥的！打开包装后太喜欢了！...', reviewAuthor: '296727733', reviewStatus: true},
				{sourceUrl: '//www.mi.com/dianyuan10000/', imgUrl: '//i1.mifile.cn/a1/T12HJvByEv1RXrhCrK!220x220.jpg', 'title': '移动电源10000mAh',
					price: '79', heat: '19.1万', reviewDesc: '美观小巧，便于携带，希望小米再接再厉！永远支持你！你...', reviewAuthor: '888846438', reviewStatus: true},
				{sourceUrl: '//www.mi.com/dianyuan10000/pro/', imgUrl: '//i1.mifile.cn/a1/T1eSZgBjVT1RXrhCrK!220x220.jpg', 'title': '移动电源10000mAh 高配版',
					price: '149', heat: '2万', reviewDesc: ' 手感超舒服，有USB C输入充电，以后不用到处换插头了', reviewAuthor: '玻璃樽81', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154400042.html', imgUrl: '//i3.mifile.cn/a4/T1x8J_BgEv1RXrhCrK.jpg', 'title': '移动电源20000mAh',
					price: '149', heat: '4.7万', reviewDesc: '一如既往的好评！支持小米！', reviewAuthor: '小丹555', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1152000009.html', imgUrl: '//i1.mifile.cn/a1/T1vSDQB4_T1RXrhCrK!220x220.jpg', 'title': '10000mAh小米移动电源保护套',
					price: '19.9', heat: '2万', reviewDesc: '可好了，能有效的保护手机了，再也不用担心移动电源被磨...', reviewAuthor: '682837881', reviewStatus: true},
				{sourceUrl: '//www.mi.com/powerstrip/', imgUrl: '//i3.mifile.cn/a4/T1jMbjB5Jv1RXrhCrK.jpg', 'title': '小米插线板（3孔位+USB）',
					price: '49', heat: '24.7万', reviewDesc: '做工沒的說，摸起來手感非常細膩，而且比起傳統的插線板...', reviewAuthor: '林岐城', reviewStatus: true},
				{sourceUrl: '//www.mi.com/chongdianqi4kou/', imgUrl: '//i1.mifile.cn/a1/T1vFEjBbWT1RXrhCrK!220x220.jpg', 'title': '小米USB充电器（4口）',
					price: '69', oldPrice: '8.8', heat: '7051', reviewDesc: '挺不错哒小巧精致非常使用，支持快充', reviewAuthor: '朋哥441035', reviewStatus: true},
				{moreUrl: '//list.mi.com/11', sourceUrl: '//item.mi.com/1154500022.html', imgUrl: '//i3.mifile.cn/a4/T1Ihd_BTCv1RXrhCrK.jpg', 'title': '小米插线板 5孔位', price: '39'}
			],
			battery: [
				{sourceUrl: '//item.mi.com/1134900527.html', imgUrl: '//i1.mifile.cn/a1/T1sRhTBsYT1RXrhCrK!220x220.jpg', 'title': 'SanDisk 16GB存储卡（Class4）',
					price: '26.9', heat: '7.9万', reviewDesc: '物美价廉，正品行货，发货迅速', reviewAuthor: 'sharph', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1153300072.html', imgUrl: '//i1.mifile.cn/a1/T1ipAvB_ZT1RXrhCrK!220x220.jpg', 'title': '原装快充套装', discountType: 'discount', discount: '享八折',
					price: '58', oldPrice: '78', heat: '0', reviewDesc: '客服妹子实话说吧！永远支持国产，永远支持小米。这圈铁...', reviewAuthor: '894039435', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154300033.html', imgUrl: '//i1.mifile.cn/a1/T1xxVTBghv1RXrhCrK!220x220.jpg', 'title': '彩虹5号电池（10粒装）',
					price: '9.9', heat: '6.9万', reviewDesc: '价格实惠，外观好看，还有盒子便于保管，不错。', reviewAuthor: 'monkeyshine', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1155000010.html', imgUrl: '//i1.mifile.cn/a1/T178EjBjVT1RXrhCrK!220x220.jpg', 'title': '彩虹7号电池（10粒装）',
					price: '9.9', heat: '4万', reviewDesc: '好用，好看。。价格实惠', reviewAuthor: '米米徳', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1151400067.html', imgUrl: '//i1.mifile.cn/a1/T16XAgB5dT1RXrhCrK!220x220.jpg', 'title': 'CR2032纽扣电池',
					price: '9', heat: '1.3万', reviewDesc: '小米把关，质量还是有得保证的，暂时还没用，先备着！', reviewAuthor: '陶都', reviewStatus: true},
				{sourceUrl: '//www.mi.com/recharger/', imgUrl: '//i3.mifile.cn/a4/T1gVCgBjDv1RXrhCrK.jpg', 'title': '紫5镍氢充电电池',
					price: '49', heat: '2367', reviewDesc: '终于出了充电电池，外形时尚，喜欢', reviewAuthor: '吴国立', reviewStatus: true},
				{sourceUrl: '//item.mi.com/1154400043.html', imgUrl: '//i1.mifile.cn/a1/T142A_BXEv1RXrhCrK!220x220.jpg', 'title': '小米车载充电器',
					price: '49', oldPrice: '8.8', heat: '3万', reviewDesc: '很好，个头小能量大，很满意', reviewAuthor: '你再猜猜啊', reviewStatus: true},
				{moreUrl: '//list.mi.com/135', sourceUrl: '//item.mi.com/1152400014.html', imgUrl: '//i1.mifile.cn/a1/T1_lKvBKZT1RXrhCrK!220x220.jpg', 'title': '红米2/红米2A能量套装', price: '69'}
			]
		}
	},
	ready () {
		this.currGoods = this.hotGoods
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
</style>
