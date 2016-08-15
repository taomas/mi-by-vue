<template>
	<div class="top-header">
		<div class="container">
			<a href="#" class="icon-mi"></a>
			<a href="#" class="pic-gif"></a>
			<div class="header-navs">
				<ul class="navs">
					<li v-for="item in navs" class="nav">
						<a href="#" class="nav-item">{{item.name}}</a>
					</li>
				</ul>
			</div>
			<div class="header-search">
				<input
					@focus="evtIptFocus"
					@blur="evtIptBlur"
					class="search-ipt" type="search" name="search" value="">
				<label class="search-btn" for="search">
					<i class="icon-search"></i>
				</label>
				<ul class="search-result clearfix">
					<li v-for="item in results">
						<span class="item-name">{{item.name}}</span>
						<span class="item-num">约有{{item.number}}件</span>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			navs: [
				{name: '小米手机'},
				{name: '红米'},
				{name: '平板 · 笔记本'},
				{name: '电视'},
				{name: '盒子 · 影音'},
				{name: '路由器'},
				{name: '智能硬件'},
				{name: '服务'},
				{name: '社区'}
			],
			results: [
				{name: '小米手机5', number: '11'},
				{name: '空气净化器2', number: '1'},
				{name: '活塞耳机', number: '4'},
				{name: '小米路由器', number: '8'},
				{name: '移动电源', number: '21'},
				{name: '运动相机', number: '3'},
				{name: '小米摄像机', number: '2'},
				{name: '小米体重秤', number: '1'},
				{name: '小米插线板', number: '13'},
				{name: '配件优惠套装', number: '32'}
			]
		}
	},
	methods: {
		evtIptFocus () {
			$('.header-search').addClass('search-active')
			$('.search-result').show()
		},
		evtIptBlur () {
			$('.header-search').removeClass('search-active')
			$('.search-result').hide()
		}
	}
}
</script>

<style scoped>
.top-header {
	width: 100%;
	height: 100px;
}

.container {
	position: relative;
	display: flex;
	flex-flow: row;
	flex-wrap: nowrap;
	justify-content: flex-start;
	align-items: center;
	width: 1226px;
	height: 100%;
	margin: 0 auto;
}

.icon-mi {
	width: 55px;
	height: 55px;
	background: url('../assets/img/icon-mi.png') no-repeat;
	background-size: 100% 100%;
}

.pic-gif {
	width: 163px;
	height: 66px;
	margin-left: 10px;
	background: url('../assets/img/win.gif') no-repeat;
	background-size: 100% 100%;
}

.header-navs {
}
.navs {
	margin: 0;
	padding: 0;
	list-style: none;
	.nav {
		display: inline-block;
		a {
			font-size: 16px;
			padding: 0 10px;
			text-decoration: none;
			color: #333;
		}
	}
}

.header-search {
	position: absolute;
	top: 23px;
	right: 0;
	width: 295px;
	height: 50px;
	border: 1px solid #e0e0e0;
	.search-ipt {
		float: left;
		width: 240px;
		height: 100%;
		border: 0;
		outline: none;
	}
	.search-btn {
		display: block;
		float: right;
		width: 50px;
		height: 100%;
		border-left: 1px solid #e0e0e0;
		cursor: pointer;
		.icon-search {
			display: block;
			width: 20px;
			height: 20px;
			margin-top: 15px;
			margin-left: 15px;
			background: url('../assets/img/icon-search.png') center center no-repeat;
			background-size: 100% 100%;
		}
		&:hover {
			background: #ff6700;
			.icon-search {
				background: url('../assets/img/icon-search-white.png') center center no-repeat;
				background-size: 100% 100%;
			}
		}
	}
}

.search-active {
	border: 1px solid #ff6700;
	.search-btn {
		border-left: 1px solid #ff6700;
	}
}

.search-result {
	display: none;
	position: absolute;
	left: -1px;
	top: 50px;
	width: 244px;
	height: auto;
	margin: 0;
	padding: 0;
	list-style: none;
	border: 1px solid #ff6700;
	li {
		padding: 7px 13px;
		width: 100%;
		height: 30px;
		box-sizing: border-box;
		cursor: pointer;
		.item-name {
			float: left;
			font-size: 12px;
		}
		.item-num {
			float: right;
			font-size: 10px;
			color: #b0b0b0;
		}
	}
}
</style>
