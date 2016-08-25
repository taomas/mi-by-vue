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
				{sourceUrl: '//list.mi.com/22', imgUrl: 'http://i3.mifile.cn/a4/ff2a2f99-2c69-4472-acc1-e16322ee79ba'},
				{sourceUrl: '//list.mi.com/23', imgUrl: 'http://i3.mifile.cn/a4/c2b64ac9-0b29-4158-a4ab-66aca1720916'}
			],
			hot: [
				{sourceUrl: '//item.mi.com/1151400027.html', imgUrl: 'http://i3.mifile.cn/a4/T1IDC_B_Kv1RXrhCrK.jpg', title: '小米V领短袖T恤 男款', price: '29', heat: '1.6万',
				reviewDesc: '穿着这衣服，真是舒服，就想抱着女朋友的感觉一样 ', reviewAuthor: '574081459', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000019.html', imgUrl: 'http://i3.mifile.cn/a4/e8f5a80c-7f57-4f7b-97fc-c446059d2381', title: '小米短袖T恤 水管工米兔', price: '29', heat: '3567',
				reviewDesc: '感觉非常不错，特别是这上边的图案，萌萌哒！', reviewAuthor: '478670150', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1162200008.html', imgUrl: 'http://i3.mifile.cn/a4/d3897b3a-59b4-4cdb-a726-f318f0ee44b6', title: '小米短袖T恤 新国货', price: '29', heat: '476',
				reviewDesc: '货品收到了！这个印花太耀眼了。', reviewAuthor: '乌之江下面', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000025.html', imgUrl: 'http://i3.mifile.cn/a4/23c8122a-3bf4-4675-abb2-aca349aa1923', title: '小米V领短袖T恤 女款', price: '29', heat: '3075',
				reviewDesc: '好穿级了，纯棉，手感不错，性价比高', reviewAuthor: '狗都爱吃肉', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161100002.html', imgUrl: 'http://i3.mifile.cn/a4/6ddc1df6-ce8e-4cb5-a26a-b5ef80f1adf7', title: '小米经典商务双肩包', price: '99', oldPrice: '39', heat: '4426',
				reviewDesc: '非常好的包包，做工精细，走线整齐，连拉链都很精致。9...', reviewAuthor: '933771817', reviewStatus: true, discount: false},
				{sourceUrl: '//www.mi.com/mimosdge/', imgUrl: 'http://i1.mifile.cn/a1/pms_1468310472.00391359!220x220.jpg ', title: '米家随身电蚊香', price: '29', oldPrice: '39', heat: '1927',
				reviewDesc: '这个真不错！我用超威蚊香片插放很容易！它使用的标准尺...', reviewAuthor: 'LGH863117', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1162800009.html', imgUrl: 'http://i3.mifile.cn/a4/5a28d943-ef5d-4920-a89a-7f1bce6c5b35', title: '米家LED随身灯 增强版', price: '19.9', oldPrice: '39', heat: '2261',
				reviewDesc: '很好用！特别是五挡开关灯，好用！方便！', reviewAuthor: '86505510', reviewStatus: true, discount: false},
				{moreUrl: '//list.mi.com/zhoubian', sourceUrl: '//item.mi.com/1144600004.html', imgUrl: 'http://i3.mifile.cn/a4/T1yo_gBm_v1RXrhCrK.jpg', title: '金属鼠标垫 小号', price: '49'}
			],
			clothes: [
				{sourceUrl: '//item.mi.com/1161000022.html', imgUrl: '//i3.mifile.cn/a4/T1i.YjBbWT1RXrhCrK.jpg', title: '小米短袖T恤 情侣米兔 女款', price: '29', heat: '1558',
				reviewDesc: '衣服质量不错，样式也不错 ', reviewAuthor: '小紅帽0809', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000027.html', imgUrl: '//i3.mifile.cn/a4/a2973973-b7f1-4431-988b-449c0d068419', title: '小米V领短袖T恤 女款', price: '29', heat: '3075',
				reviewDesc: '好穿级了，纯棉，手感不错，性价比高', reviewAuthor: '狗都爱吃肉', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000018.html', imgUrl: '//i3.mifile.cn/a4/T1ReJ_B_Kv1RXrhCrK.jpg', title: '小米短袖T恤 小熊米兔', price: '29', heat: '4512',
				reviewDesc: '女朋友说了，衣服不错就是人丑了点。', reviewAuthor: 'Mi_940790865', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000020.html', imgUrl: '//i3.mifile.cn/a4/357bebdd-6e77-4c43-a33c-b8287caace2e', title: '小米短袖T恤 水管工米兔', price: '29', heat: '3567',
				reviewDesc: '感觉非常不错，特别是这上边的图案，萌萌哒！', reviewAuthor: '478670150', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000032.html', imgUrl: '//i3.mifile.cn/a4/T1GXYgBgJv1RXrhCrK.jpg', title: '小米短袖POLO衫 女款', price: '59', heat: '1023',
				reviewDesc: '颜色很正，质地好，我继续支持小米！', reviewAuthor: 'Mi_657996558', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1161000021.html', imgUrl: '//i3.mifile.cn/a4/T1MIC_BTLv1RXrhCrK.jpg', title: '小米短袖T恤 轻松米兔', price: '29', heat: '4629',
				reviewDesc: '便宜好货，胜过nike，做工精细，新国货 ，小米加油！', reviewAuthor: '蓝海苑', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{sourceUrl: '//item.mi.com/1161000035.html', imgUrl: '//i3.mifile.cn/a4/T1m3CgBXJv1RXrhCrK.jpg', title: '小米短袖T恤 摇滚星球', price: '29', heat: '2622',
				reviewDesc: '纯棉的穿的很舒服！样式好看！', reviewAuthor: '434388030', reviewStatus: true, oldPrice: '39', discountType: 'discount', discount: '享8折'},
				{moreUrl: '//list.mi.com/22', sourceUrl: '//item.mi.com/1161000034.html', imgUrl: '//i3.mifile.cn/a4/T1L_D_B7Jv1RXrhCrK.jpg', title: '小米短袖T恤  五彩环', price: '29'}
			],
			rabbit: [
				{sourceUrl: '//item.mi.com/1162200024.html', imgUrl: '//i1.mifile.cn/a1/pms_1464943812.60215816!220x220.jpg', title: '超脑米兔钥匙扣', price: '29', heat: '328',
				reviewDesc: '最有科技感的一款米兔，小米也好像很久没出身高8CM的...', reviewAuthor: '小龙龙', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1162200023.html', imgUrl: '//i1.mifile.cn/a1/pms_1464947945.39918897!220x220.jpg', title: '拳击手米兔', price: '49', heat: '80',
				reviewDesc: '拳击手米兔～(LIGHTWEIGHT BOXING ...', reviewAuthor: 'Bestdiao-HC', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1162000069.html', imgUrl: '//i1.mifile.cn/a1/pms_1463975728.16077005!220x220.jpg', title: '悟空米兔', price: '49', heat: '229',
				reviewDesc: '不错，我非常喜欢，斩妖除魔。猴年大吉。', reviewAuthor: '丛晓宇', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1162000070.html', imgUrl: '//i1.mifile.cn/a1/pms_1463973922.4853847!220x220.jpg ', title: '飞行员米兔屏幕擦挂饰', price: '29', heat: '204',
				reviewDesc: '做工精致，好喜欢好喜欢', reviewAuthor: '刘冠佐', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1134900318.html', imgUrl: '//i1.mifile.cn/a1/T1dRZTB_xT1RXrhCrK!220x220.jpg', title: '经典版米兔', price: '29', heat: '3.9万',
				reviewDesc: '可爱(⊙o⊙)哦，好多女孩向我要呢', reviewAuthor: '273294452', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1161200074.html', imgUrl: '//i3.mifile.cn/a4/T1zVZjBmJv1RXrhCrK.jpg', title: '文艺版米兔', price: '49', heat: '263',
				reviewDesc: '好可爱的一直米兔，衣服做的不错，而且合身', reviewAuthor: '小米东升哥', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1141500018.html', imgUrl: '//i3.mifile.cn/a4/T1qvEgBKKv1RXrhCrK.jpg', title: '30cm坐姿米兔', price: '49', heat: '971',
				reviewDesc: '很好很可爱。家里人很喜欢。值得拥有！', reviewAuthor: '247908452', reviewStatus: true, discount: false},
				{moreUrl: 'http://mitu.mi.com/', sourceUrl: '//item.mi.com/1144400047.html', imgUrl: '//i1.mifile.cn/a1/T1MBhvBm_T1RXrhCrK!220x220.jpg', title: '黑猫米兔', price: '39'}
			],
			around: [
				{sourceUrl: '//item.mi.com/1144600004.html', imgUrl: '//i3.mifile.cn/a4/T1yo_gBm_v1RXrhCrK.jpg', title: '金属鼠标垫 小号', price: '49', heat: '8397',
				reviewDesc: '我的鼠标垫时尚时尚最时尚，摩擦摩擦！', reviewAuthor: '102733048', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1153700036.html', imgUrl: '//i1.mifile.cn/a1/T1fADvByVv1RXrhCrK!220x220.jpg', title: '小米皮质记事本', price: '19', heat: '5018',
				reviewDesc: '这是我有史以来看到的最漂亮的笔记本，不管是皮的材质，...', reviewAuthor: 'zhangqy112233', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1162800009.html', imgUrl: 'http://i3.mifile.cn/a4/5a28d943-ef5d-4920-a89a-7f1bce6c5b35', title: '米家LED随身灯 增强版', price: '19.9', heat: '2261',
				reviewDesc: '很好用！特别是五挡开关灯，好用！方便！', reviewAuthor: '86505510', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1134900194.html', imgUrl: '//i1.mifile.cn/a1/T1UmxTBQhv1RXrhCrK!220x220.jpg', title: '手机支架 小蜜蜂', price: '19', heat: '7万',
				reviewDesc: '自从有了你再也不用担心手会酸了，就是离不开它了，这可...', reviewAuthor: '861173399', reviewStatus: true, discount: false},
				{sourceUrl: '//www.mi.com/transformers/', imgUrl: '//i1.mifile.cn/a1/pms_1463971828.3961404!220x220.jpg', title: '变形金刚特别版声波', price: '169', heat: '1691',
				reviewDesc: '平板变成金刚！超乎想象！好酷！喜欢，希望还有系列的产...', reviewAuthor: 'Paul', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1134900289.html', imgUrl: '//i1.mifile.cn/a1/T198bTBbAv1RXrhCrK!220x220.jpg', title: '小米百变随身杯', price: '39', heat: '1.3万',
				reviewDesc: '百变杯随心杯，把家人萌照贴上，真是暖在心喔。', reviewAuthor: '167050409', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1154900068.html', imgUrl: '//i1.mifile.cn/a1/T1eKdgB4xv1RXrhCrK!220x220.jpg', title: '小米电源线收纳盒', price: '49 ', heat: '2045',
				reviewDesc: '简洁大方，支持小米。', reviewAuthor: '古国龙', reviewStatus: true, discount: false},
				{moreUrl: '//list.mi.com/20', sourceUrl: '//item.mi.com/1161000016.html', imgUrl: '//i3.mifile.cn/a4/T15AxgByEv1RXrhCrK.jpg', title: '小米鼠标垫', price: '4.9'}
			],
			bags: [
				{sourceUrl: '//item.mi.com/1153700020.html', imgUrl: '//i3.mifile.cn/a4/T1RRCjBKJv1RXrhCrK.jpg', title: '90分旅行箱 20寸', price: '299', oldPrice: '', heat: '1.4万',
				reviewDesc: '这箱子很好，外观漂亮，实用性强。很轻，有点软但不影响...', reviewAuthor: '子书雁', reviewStatus: true, discountType: 'free', discount: '免邮费'},
				{sourceUrl: '//item.mi.com/1155100013.html', imgUrl: '//i3.mifile.cn/a4/T1TvJ_B_Kv1RXrhCrK.jpg', title: '90分旅行箱 24寸', price: '349', oldPrice: '', heat: '1.1万',
				reviewDesc: '设计简约好看，轮子静音顺滑。前几天去香港刚好用上了', reviewAuthor: '黄黄志刚', reviewStatus: true, discountType: 'free', discount: '免邮费'},
				{sourceUrl: '//item.mi.com/1162500014.html', imgUrl: '//i1.mifile.cn/a1/pms_1466665347.53966019!220x220.jpg', title: '小米轻动系百搭多用背包', price: '39', oldPrice: '', heat: '1971',
				reviewDesc: '不错很喜欢，材料质地很好，收纳绝对方便，推荐购买', reviewAuthor: '糖胖子', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1153800038.html', imgUrl: '//i3.mifile.cn/a4/T1G9Y_BmCv1RXrhCrK.jpg', title: '90分便携收纳袋', price: '29', oldPrice: '', heat: '2431',
				reviewDesc: '小巧实用，做工不错，与描述一致，继续关注！', reviewAuthor: '新顽主爹', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1161100002.html', imgUrl: 'http://i3.mifile.cn/a4/6ddc1df6-ce8e-4cb5-a26a-b5ef80f1adf7', title: '小米经典商务双肩包', price: '99', oldPrice: '', heat: '4426',
				reviewDesc: '做工精细，走线整齐，连拉链都很精致。9...', reviewAuthor: '933771817', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1154400038.html', imgUrl: '//i1.mifile.cn/a1/T1a3DvB7hv1RXrhCrK!220x220.jpg', title: '小米极简都市双肩包', price: '149', oldPrice: '', heat: '1.4万',
				reviewDesc: '设计很美，里面很多分隔，女儿很喜欢', reviewAuthor: '良槎水月宫', reviewStatus: true, discount: false},
				{sourceUrl: '//item.mi.com/1154400037.html', imgUrl: '//i1.mifile.cn/a1/T1jZD_BmAv1RXrhCrK!220x220.jpg', title: '小米多功能电脑包', price: '199', oldPrice: '', heat: '1617',
				reviewDesc: '比想象中的实用，好多袋子，出差的选择。不用一堆东西搅...', reviewAuthor: '105870213', reviewStatus: true, discount: false},
				{moreUrl: '//list.mi.com/23', sourceUrl: '//item.mi.com/1134900281.html', imgUrl: '//i1.mifile.cn/a1/T1nmhTBTKT1RXrhCrK!220x220.jpg', title: '小米商务真皮钱包', price: '99'}
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
