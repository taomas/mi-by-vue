<template>
	<div class="product-container">
		<goods-header :title="title"></goods-header>
		<div class="box-bd">
			<ul class="content-list clearfix">
				<li>
					<template v-for="content in contents">
						<good-content-slide :content="content"></good-content-slide>
					</template>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
import GoodsHeader from './common/GoodsHeader'
import GoodsContentSlide from './common/GoodsContentSlide'
export default {
	data () {
		return {
			currPage: 0,
			title: '内容',
			contents: [
				{
					title: '图书',
					type: 'book',
					list: [
						{sourceUrl: 'http://www.duokan.com/book/115222', title: '哈利·波特与魔法石', desc: '哈利波特来了', imgUrl: '//i3.mifile.cn/a4/8e3584b6-3169-41c6-9356-939ec79aac2b', type: 0},
						{sourceUrl: 'http://www.duokan.com/special/7812', title: '特价专区', desc: '精选畅销好书，特价促销，天天更新，天天特价！', price: '限时优惠', imgUrl: '//i3.mifile.cn/a4/T1dlVgBbbT1RXrhCrK.jpg', type: 1},
						{sourceUrl: 'http://www.duokan.com/list/9-1', title: '杂志专区', desc: '纸媒杂志＋互联网杂志，你想看的这都有！', price: '同步新刊上线', imgUrl: '//i3.mifile.cn/a4/T1R3WgBjKT1RXrhCrK.jpg', type: 1},
						{sourceUrl: 'http://www.duokan.com/list/1-1?from=xiaomi', desc1: '海量好书，享受精品阅读时光', desc2: '漂亮的中文排版，千万读者选择！', btnTxt: '前往多看阅读', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				},
				{
					title: 'MIUI主题',
					type: 'theme',
					list: [
						{sourceUrl: 'http://zhuti.xiaomi.com/detail/4ecf4ebb-7cba-4142-96aa-6b8deb2426ef', title: '新世纪福音战士OL', desc: 'EVA手游正版授权，同名主题，高能来袭！', price: '免费', imgUrl: 'http://i3.mifile.cn/a4/7d47dde1-60fb-4ff3-8fa1-364cfc452457', type: 1},
						{sourceUrl: 'http://zhuti.xiaomi.com/detail/d6277519-ca46-420c-ab09-060f6d293f94', title: '世界就在这里', desc: '“青春的世界里，每一刻都要用尽全力欢呼”', price: '免费', imgUrl: 'http://i3.mifile.cn/a4/b2c8ca37-4ba8-4af8-b87e-91847980a278', type: 1},
						{sourceUrl: 'http://zhuti.xiaomi.com/detail/13df18d4-e52c-4a61-82e3-97014f21bd77', title: '不悔剑三', desc: '精品剑网三同人主题 浪漫武侠 共闯天涯', price: '3米币', imgUrl: 'http://i3.mifile.cn/a4/10af68f9-3012-48bb-85b1-ad3b0646dfdb', type: 1},
						{sourceUrl: 'http://zhuti.xiaomi.com/?from=mi', desc1: '众多个性主题、百变锁屏与自由桌面', desc2: '让你的手机与众不同！', btnTxt: '前往MIUI主题市场', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				},
				{
					title: '游戏',
					type: 'game',
					list: [
						{sourceUrl: 'http://ljm.mi.com/?channel=meng_1084_1_android', title: '老九门', desc: '盗墓笔记前传上线', price: '免费', imgUrl: 'http://i3.mifile.cn/a4/6032cb36-587f-4366-89ef-aefed2546552', type: 1},
						{sourceUrl: 'http://game.xiaomi.com/miyou/index.html', title: '米柚手游模拟器', desc: '在电脑上玩遍小米所有手游', price: '免费', imgUrl: '//i3.mifile.cn/a4/T1czW_BXCv1R4cSCrK.png', type: 1},
						{sourceUrl: 'http://game.xiaomi.com/app-appdetail--app_id__581412.html', title: '剑侠情缘', desc: '玩剑侠情缘手游，领666壕礼！！', price: '免费', imgUrl: 'http://i3.mifile.cn/a4/010948ae-bd48-49c6-af12-4ec8c4a0c829', type: 1},
						{sourceUrl: 'http://game.xiaomi.com/index.php?c=index&a=run', desc1: '免费下载海量的手机游戏', desc2: '天天都有现金福利赠送', btnTxt: '前往小米游戏商店', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-game.jpg', type: 2}
					]
				},
				{
					title: '应用',
					type: 'app',
					list: [
						{sourceUrl: 'http://app.mi.com/subject/168797', title: '2015年度应用', desc: '2015年度应用', price: '免费', imgUrl: '//i3.mifile.cn/a4/T1YyJgBCYv1R4cSCrK.png', type: 1},
						{sourceUrl: 'http://app.mi.com/subject/168798', title: '2015年度游戏', desc: '2015年度游戏', price: '免费', imgUrl: '//i3.mifile.cn/a4/T1eaxgB4Ev1R4cSCrK.png', type: 1},
						{sourceUrl: 'http://app.mi.com/subject/167924', title: '小米应用', desc: '小米出品 必属精品', price: '免费', imgUrl: '//i3.mifile.cn/a4/T15VZvB5Kv1R4cSCrK.png', type: 1},
						{sourceUrl: 'http://app.mi.com/?from=mi', desc1: '帮助小米手机和其他安卓手机用户', desc2: '发现好用的安卓应用', btnTxt: '前往小米应用商店', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-app.jpg', type: 2}
					]
				}]
		}
	},
	components: {
		'goods-header': GoodsHeader,
		'good-content-slide': GoodsContentSlide
	}
}
</script>

<style>
.product-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
</style>
