<template>
  <div class="top-sub">
		<div class="sub-1">
			<ul class="channels">
				<li class="channel">
					<i class="fa fa-mobile fa-fw sub-icon"></i>
					<a href="#">选购手机</a>
				</li>
				<div class="line-vertical">
				</div>
				<li class="channel">
					<i class="fa fa-gift fa-fw sub-icon"></i>
					<a href="#">企业团购</a>
				</li>
				<div class="line-vertical">
				</div>
				<li class="channel">
					<i class="fa fa-refresh fa-fw sub-icon"></i>
					<a href="#">官翻产品</a>
				</li>
				<div class="line-horizontal">
				</div>
				<div class="line-horizontal">
				</div>
				<div class="line-horizontal">
				</div>
				<li class="channel">
					<i class="fa fa-credit-card fa-fw sub-icon"></i>
					<a href="#">小米移动</a>
				</li>
				<div class="line-vertical">
				</div>
				<li class="channel">
					<i class="fa fa-recycle fa-fw sub-icon"></i>
					<a href="#">以旧换新</a>
				</li>
				<div class="line-vertical">
				</div>
				<li class="channel">
					<i class="fa fa-credit-card-alt fa-fw sub-icon"></i>
					<a href="#">话费充值</a>
				</li>
			</ul>
		</div>
		<ul class="subs">
			<li>
				<a href="#" class="sub-item sub-2">
					<img src="http://i3.mifile.cn/a4/69f0776a-262b-4d88-853e-212a19e9f323" alt="" />
				</a>
			</li>
			<li>
				<a href="#" class="sub-item sub-3">
					<img src="http://i3.mifile.cn/a4/d7136426-ce57-432a-aa12-8224546e0530" alt="" />
				</a>
			</li>
			<li>
				<a href="#" class="sub-item sub-4">
					<img src="http://i3.mifile.cn/a4/615c4599-fd37-4e61-aef6-c30b73330237" alt="" />
				</a>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data () {
		return {
		}
	},
	methods: {
		evtSubEnter (selector) {
		}
	}
}
</script>

<style scoped>
.top-sub {
	position: relative;
	width: 1226px;
	height: auto;
	margin: 14px auto 0;
}
.sub-1 {
	float: left;
	width: 234px;
	height: 170px;
	background: #5f5750;
}
.channels {
	display: flex;
	flex-flow: row wrap;
	justify-content: flex-start;
	align-items: flex-start;
	list-style: none;
	margin: 0;
	padding: 3px;
	.channel {
		width: 75px;
		height: 82px;
		cursor: pointer;
		&:hover{
			a {
				color: #fff;
			}
			.sub-icon {
				color: #fff;
			}
		}
		a {
			display: block;
			width: 75px;
			font-size: 12px;
			text-align: center;
			text-decoration: none;
			color: rgba(255,255,255,0.7);
		}
	}
	.sub-icon {
		width: 75px;
		height: 24px;
		margin-top: 18px;
		margin-bottom: 5px;
		font-size: 20px;
		color: rgba(255,255,255,0.7);
	}
}

.subs {
	display: flex;
	flex-flow: row nowrap;
	justify-content: flex-start;
	margin: 0;
	padding: 0;
	list-style: none;
	li {
		width: 316px;
		height: 170px;
		margin-left: 15px;
	}
	.sub-item {
		display: block;
		transition: all 0.3s;
		&:hover {
			box-shadow: 0 5px 30px #ccc;
		}
		img {
			display: block;
			width: 316px;
			height: 170px;
		}
	}
}

.line-vertical {
	width: 1px;
	height: 60px;
	margin-top: 10px;
	background: rgba(255,255,255,0.1);
}

.line-horizontal {
	width: 60px;
	height: 1px;
	margin: 0 8px;
	background: rgba(255,255,255,0.1);
}
</style>
