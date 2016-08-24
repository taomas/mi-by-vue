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
						<a class="goods-link" :href="item.sourceUrl">
							<img :src="item.imgUrl" alt="" />
							<div class="text-name">
								{{item.name}}
							</div>
						</a>
						<a class="goods-buy-link"
							v-show="item.buyStatus"
							:href="item.buyUrl">
								选购
						</a>
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
				{sourceUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://i3.mifile.cn/a4/bc62a28f-de64-4eee-853b-36772a97f67e'},
				{sourceUrl: '//item.mi.com/buyphone/hongmi3s', imgUrl: 'http://i3.mifile.cn/a4/ba4939c9-fc0a-4916-bddc-726fa00f7e9b'},
				{sourceUrl: '//item.mi.com/buyphone/mimax', imgUrl: 'http://i3.mifile.cn/a4/9ced2c9e-f685-4918-9b2a-402af2d2039f'},
				{sourceUrl: '//item.mi.com/buyphone/note3', imgUrl: 'http://i3.mifile.cn/a4/f4bee59d-85a5-498f-ae57-a2cabe6aeb5b'},
				{sourceUrl: '//item.mi.com/buymitv/48', imgUrl: 'http://i3.mifile.cn/a4/98fc8a58-c35c-475e-89cb-b8fe1659817f'}
			],
			phones: [
				{sourceUrl: '//www.mi.com/mi5/', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '小米手机5', buyStatus: true},
				{sourceUrl: '//www.mi.com/mimax/', buyUrl: '//item.mi.com/buyphone/mimax', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/maxbar80.jpg?width=40&height=40', name: '小米Max', buyStatus: true},
				{sourceUrl: '//www.mi.com/note3/pro/', buyUrl: '//item.mi.com/buyphone/note3', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/note3.jpg?width=40&height=40', name: '小米Note3', buyStatus: true},
				{sourceUrl: '//www.mi.com/hongmi3s/', buyUrl: '//item.mi.com/buyphone/hongmi3s', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/hm3s80x80.jpg?width=40&height=40', name: '红米手机3S', buyStatus: true},
				{sourceUrl: '//www.mi.com/redmipro/', buyUrl: '//item.mi.com/buyphone/redmipro/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hongmi3.jpg?width=40&height=40', name: '红米Pro', buyStatus: true},
				{sourceUrl: '//www.mi.com/hongmi3/', buyUrl: '//item.mi.com/buyphone/hongmi3/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/list/mi5bar80.jpg?width=40&height=40', name: '红米手机3', buyStatus: true},
				{sourceUrl: '//www.mi.com/hongmi3x/', buyUrl: '//item.mi.com/buyphone/hongmi3x', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/3X80.jpg?width=40&height=40', name: '红米手机3X', buyStatus: true},
				{sourceUrl: '//heyue.mi.com/', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/heyue.jpg?width=40&height=40', name: '合约机', buyStatus: false},
				{sourceUrl: '//www.mi.com/compare/', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/compare.jpg?width=40&height=40', name: '对比手机', buyStatus: false},
				{sourceUrl: '//www.mi.com/mimobile/', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/mimobile.jpg?width=40&height=40', name: '小米移动 电话卡', buyStatus: false}
			],
			computer: [
				{sourceUrl: '//www.mi.com/mibookair/', buyUrl: '//item.mi.com/buymibook/air', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben80.jpg?width=40&height=40', name: '小米笔记本Air', buyStatus: true},
				{sourceUrl: '//www.mi.com/mipad2/', buyUrl: '//item.mi.com/static/buymipad', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pad2.png?width=40&height=40', name: '小米平板2', buyStatus: true},
				{sourceUrl: '//item.mi.com/1163000011.html', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/usbzjqggg80.jpg?width=40&height=40', name: 'USB-C转接器', buyStatus: false},
				{sourceUrl: '//item.mi.com/1163100001.html', buyUrl: '//item.mi.com/buyphone/mi5', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/neidanbao80.jpg?width=40&height=40', name: '小米笔记本内胆包', buyStatus: false}
			],
			box: [
				{sourceUrl: '//www.mi.com/mitv3s/43/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/4380side.jpg?width=40&height=40', name: '小米电视 43英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitv3s/48/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/mitv3s48.jpg?width=40&height=40', name: '小米电视 48英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitv3/55/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv3-55.jpg?width=40&height=40', name: '小米电视 55英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitv3/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv60.jpg?width=40&height=40', name: '小米电视 60英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitv3s/65/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/6580side.jpg?width=40&height=40', name: '小米电视 65英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitv3/70/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tv70.png?width=40&height=40', name: '小米电视 70英寸', buyStatus: false},
				{sourceUrl: '//www.mi.com/tvzj/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tvzj.jpg?width=40&height=40', name: '小米电视主机', buyStatus: false},
				{sourceUrl: '//www.mi.com/hezi3s/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezizengqiangban80side.jpg?width=40&height=40', name: '小米盒子3 增强版', buyStatus: false},
				{sourceUrl: '//www.mi.com/hezi3/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezis.jpg?width=40&height=40', name: '小米盒子3', buyStatus: false},
				{sourceUrl: '//www.mi.com/hezimini/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hezimini.jpg?width=40&height=40', name: '小米盒子 mini', buyStatus: false},
				{sourceUrl: '//item.mi.com/1154100018.html', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/diyinpao.jpg?width=40&height=40', name: '小米低音炮', buyStatus: false},
				{sourceUrl: '//www.mi.com/shb/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/shb.jpg?width=40&height=40', name: '蓝牙手柄', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=yinxiang', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/zuheyinxiang80side.jpg?width=40&height=40', name: '家庭音响', buyStatus: false},
				{sourceUrl: '//list.mi.com/tvboxpj', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/dianshipeijian.jpg?width=40&height=40', name: '电视盒子配件', buyStatus: false}
			],
			router: [
				{sourceUrl: '//www.mi.com/mivr1c/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/vr8080.jpg?width=40&height=40', name: '小米VR眼镜玩具版', buyStatus: false},
				{sourceUrl: '//www.mi.com/miuav/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/wurenji80.jpg?width=40&height=40', name: '小米无人机', buyStatus: false},
				{sourceUrl: '//www.mi.com/miwifi3/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/luyouqi-80.jpg?width=40&height=40', name: '小米路由器', buyStatus: false},
				{sourceUrl: '//www.mi.com/scooter/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/list/scooter.jpg?width=40&height=40', name: '九号平衡车', buyStatus: false},
				{sourceUrl: '//www.mi.com/dianfanbao/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/dianfanbao-80.jpg?width=40&height=40', name: '米家压力IH电饭煲', buyStatus: false},
				{sourceUrl: '//www.mi.com/kettle/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/shuihu80.jpg?width=40&height=40', name: '米家恒温电水壶', buyStatus: false},
				{sourceUrl: '//www.mi.com/mibicycle/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/zxc80-80.jpg?width=40&height=40', name: '电助力折叠自行车', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=shexiangji', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/xiaobai80.jpg?width=40&height=40', name: '摄像机', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=jinghuaqilvxin', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/jinghuaqilvxin80.jpg?width=40&height=40', name: '净化器及滤芯', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=water', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/jingshuiqiandlvxin-80.jpg?width=40&height=40', name: '净水器及滤芯', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=xueyaji', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/xueyaji-80.jpg?width=40&height=40', name: '血压计', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=smartlamp', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/zhinengdeng-80.jpg?width=40&height=40', name: '智能灯', buyStatus: false},
				{sourceUrl: '//www.mi.com/mitu/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/gushiji80.jpg?width=40&height=40', name: '米兔智能故事机', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/smartsuit', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/zhinengjiatingtaozhuang-80.jpg?width=40&height=40', name: '智能家庭组合', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/shouhuan', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/shouhuan280.jpg?width=40&height=40', name: '手环及配件', buyStatus: false},
				{sourceUrl: '//www.mi.com/scale/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/scale.jpg?width=40&height=40', name: '体重秤', buyStatus: false},
				{sourceUrl: '//www.mi.com/mituwatch/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/shoubiao3-80.jpg?width=40&height=40', name: '米兔儿童电话手表', buyStatus: false},
				{sourceUrl: '//list.mi.com/26?cfrom=search', imgUrl: 'http://c1.mifile.cn/f/i/g/doodle/znyjdaohang.jpg?width=40&height=40', name: '全部智能硬件', buyStatus: false}
			],
			power: [
				{sourceUrl: '//www.mi.com/dianyuan/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/dianyuan.jpg?width=40&height=40', name: '小米移动电源', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/tag?id=powerstrip', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/powerscript.jpg?width=40&height=40', name: '小米插线板', buyStatus: false},
				{sourceUrl: '//list.mi.com/13', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/yidongdianyuan.jpg?width=40&height=40', name: '品牌移动电源', buyStatus: false},
				{sourceUrl: '//list.mi.com/dyfj', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/dianyuanfujian.jpg?width=40&height=40', name: '移动电源附件', buyStatus: false},
				{sourceUrl: '//list.mi.com/14', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/charger80.jpg?width=40&height=40', name: '电池', buyStatus: false},
				{sourceUrl: '//list.mi.com/15', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/chongdianqi-80.jpg?width=40&height=40', name: '充电器', buyStatus: false},
				{sourceUrl: '//item.mi.com/1154300033.html', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/5Battery1.jpg?width=40&height=40', name: '彩虹5号电池', buyStatus: false},
				{sourceUrl: '//item.mi.com/1155000010.html', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/7Battery1.jpg?width=40&height=40', name: '彩虹7号电池', buyStatus: false}
			],
			headset: [
				{sourceUrl: '//www.mi.com/headphone/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/headphone.jpg?width=40&height=40', name: '小米头戴式耳机', buyStatus: false},
				{sourceUrl: '//www.mi.com/quantie/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/quantie.jpg?width=40&height=40', name: '小米圈铁耳机', buyStatus: false},
				{sourceUrl: '//www.mi.com/capsuleearphone/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/jiaonang80.jpg?width=40&height=40', name: '小米胶囊耳机', buyStatus: false},
				{sourceUrl: '//www.mi.com/huosai2/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/jichuban-80.jpg?width=40&height=40', name: '小米活塞耳机 基础版', buyStatus: false},
				{sourceUrl: '//www.mi.com/bluetooth-headset/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/bluetoothheadset.jpg?width=40&height=40', name: '小米蓝牙耳机', buyStatus: false},
				{sourceUrl: '//list.mi.com/18', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/pinpai80.jpg?width=40&height=40', name: '品牌耳机', buyStatus: false},
				{sourceUrl: '//www.mi.com/pocketaudio/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pocketaudio.png?width=40&height=40', name: '小米蓝牙音箱', buyStatus: false},
				{sourceUrl: '//www.mi.com/littleaudio/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/suishen-80.jpg?width=40&height=40', name: '小米随身蓝牙音箱', buyStatus: false},
				{sourceUrl: '//www.mi.com/yinxiang/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/xiaogangpao2-hei-80.jpg?width=40&height=40', name: '小钢炮音箱 2', buyStatus: false},
				{sourceUrl: '//www.mi.com/speaker/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/qignchungangpao-80.jpg?width=40&height=40', name: '小钢炮音箱 青春版', buyStatus: false},
				{sourceUrl: '//item.mi.com/1154400010.html', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/fanghezi.jpg?width=40&height=40', name: '小米方盒子音箱', buyStatus: false},
				{sourceUrl: '//item.mi.com/1163100008.html', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/mituyinx80.jpg?width=40&height=40', name: '小米米兔音箱', buyStatus: false},
				{sourceUrl: '//www.mi.com/radio/', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/radio80side.jpg?width=40&height=40', name: '网络收音机', buyStatus: false},
				{sourceUrl: '//list.mi.com/accessories/soundbox', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/pinpaiyinxiang.jpg?width=40&height=40', name: '品牌音箱', buyStatus: false}
			],
			foil: [
				{sourceUrl: '//list.mi.com/9', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/tiemo.jpg?width=40&height=40', name: '贴膜', buyStatus: false},
				{sourceUrl: '//list.mi.com/8', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/baohu.jpg?width=40&height=40', name: '保护套/保护壳', buyStatus: false},
				{sourceUrl: '//list.mi.com/2', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/hougai.jpg?width=40&height=40', name: '后盖', buyStatus: false},
				{sourceUrl: '//list.mi.com/3', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/video/tiezhi80.jpg?width=40&height=40', name: '背贴', buyStatus: false}
			],
			line: [
				{sourceUrl: '//list.mi.com/16', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/xiancai.jpg?width=40&height=40', name: '线材', buyStatus: false},
				{sourceUrl: '//search.mi.com/search_%E8%87%AA%E6%8B%8D%E6%9D%86', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/zipaigan.jpg?width=40&height=40', name: '自拍杆', buyStatus: false},
				{sourceUrl: '//list.mi.com/5', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/zhijia.jpg?width=40&height=40', name: '手机支架', buyStatus: false},
				{sourceUrl: '//list.mi.com/27', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/cunchu.jpg?width=40&height=40', name: '存储卡', buyStatus: false}
			],
			bags: [
				{sourceUrl: '//list.mi.com/23', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/xiangbao-80.jpg?width=40&height=40', name: '箱包', buyStatus: false},
				{sourceUrl: '//search.mi.com/search_%E6%97%85%E8%A1%8C%E7%AE%B1', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/lvxingxiang.jpg?width=40&height=40', name: '90分旅行箱', buyStatus: false},
				{sourceUrl: '//list.mi.com/22', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/fuzhuang-80.jpg?width=40&height=40', name: '服饰', buyStatus: false}
			],
			rabbit: [
				{sourceUrl: 'http://mitu.mi.com/', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/mitu-80.jpg?width=40&height=40', name: '米兔玩偶', buyStatus: false},
				{sourceUrl: '//list.mi.com/59', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/shubiaodian-80.jpg?width=40&height=40', name: '鼠标垫', buyStatus: false},
				{sourceUrl: '//list.mi.com/24', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/sidebar/zhoubian1.jpg?width=40&height=40', name: '生活周边', buyStatus: false},
				{sourceUrl: '//www.mi.com/zazhi/index.html', imgUrl: 'http://c1.mifile.cn/f/i/g/2015/cn-index/zazhi-80-80.jpg?width=40&height=40', name: '《小米》杂志', buyStatus: false}
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
	border: 1px solid #e0e0e0;
	box-shadow: 3px 8px 16px rgba(0,0,0,0.18);
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
		padding: 0 20px 0 20px;
		box-sizing: border-box;
		background: #fff;
		cursor: pointer;
		.goods-link {
			display: flex;
			flex-flow: row nowrap;
			justify-content: flex-start;
			align-items: center;
			width: 170px;
		}
		.text-name {
			padding-left: 10px;
			font-size: 14px;
		}
		.goods-buy-link {
			display: block;
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
