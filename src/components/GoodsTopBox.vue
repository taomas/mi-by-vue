<template>
  <div class="boxs-container">
    <div class="boxs">
      <div class="boxs-top clearfix">
        <h3 class="top-title">智能硬件</h3>
        <a href="//www.mi.com/smart/" target="_blank">
          <span class="top-sub">
            查看全部
            <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
          </span>
        </a>
      </div>
      <div class="boxs-content clearfix">
        <div class="box-left">
          <a href="http://www.mi.com/scooter/" target="_blank">
            <img src="http://i3.mifile.cn/a4/124d82cc-cfce-44ab-b711-28b21be81683" alt="" />
          </a>
        </div>
        <div class="box-right">
          <ul class="box-list">
            <li class="box-item" v-for="good in goods">
              <span class="discount-label"
                :class="good.discountType">{{good.discount}}</span>
              <a :href="good.sourceUrl" target="_blank">
                <img :src="good.imgUrl" alt="" />
                <h3 class="box-title">{{good.title}}</h3>
              </a>
              <p class="box-desc">
                {{good.desc}}
              </p>
              <p class="box-price">
                {{good.price}}元
                <template v-if="good.discountType === 'discount'">
                  <span class="old-price">
                    {{good.oldPrice}}元
                  </span>
                </template>
              </p>
            </li>
          </ul>
        </div>
      </div>
  	</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      goods: [
        {sourceUrl: '//item.mi.com/1161200059.html', imgUrl: 'http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg', title: '小米路由器3', desc: '四天线设计，更安全更稳定', price: '149', discountType: 'free', discount: '免邮费'},
        {sourceUrl: '//www.mi.com/mibicycle/', imgUrl: 'http://i3.mifile.cn/a4/2b69b930-a2fd-4d09-a46a-8690cb79f764', title: '电助力折叠自行车', desc: '力矩传感电助力，让城市出行轻松有趣', price: '149', discountType: 'new', discount: '新品'},
        {sourceUrl: '//www.mi.com/mitu/', imgUrl: 'http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg', title: '米兔智能故事机', desc: '能说会道，宝宝的好玩伴', price: '199', discountType: 'new', discount: '新品'},
        {sourceUrl: '//www.mi.com/water2/', imgUrl: '//i3.mifile.cn/a4/T1zTK_Bbhv1RXrhCrK.jpg', title: '小米净水器', desc: '厨下式 RO反渗透直出纯净水，包邮包安装', price: '1999'},
        {sourceUrl: '//www.mi.com/ihealth/ ', imgUrl: 'http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg', title: 'iHealth智能血压计（蓝牙版）', desc: '送给父母的健康礼物 测血压仅需1步', price: '199'},
        {sourceUrl: '//www.mi.com/dianfanbao/', imgUrl: 'http://i1.mifile.cn/a1/T1OVC_ByY_1RXrhCrK!220x220.jpg', title: '米家压力IH电饭煲', desc: '智能烹饪，3L 容量', price: '999'},
        {sourceUrl: '//item.mi.com/1163200015.html', imgUrl: 'http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg', title: '全系智能套装限时款', desc: '开启你的智能生活', price: '292', oldPrice: '325', discountType: 'discount', discount: '享九折'},
        {sourceUrl: '//list.mi.com/accessories/tag?id=guangganban', imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99'}
      ]
    }
  }
}
</script>

<style scoped>

.boxs-container {
  width: 100%;
  height: auto;
  padding-top: 60px;
  margin-bottom: 26px;
  background: #f5f5f5;
}

.boxs {
  position: relative;
  width: 1226px;
  height: auto;
  margin: 0 auto;
}

.boxs-top {
  width: 100%;
  height: 58px;
}

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
  display: block;
  font-size: 16px;
  line-height: 58px;
  color: #424242;
  cursor: pointer;
  .sub-icon {
    color: #b0b0b0;
    font-size: 20px;
  }
  &:hover {
    color: #ff6700;
    .sub-icon {
      color: #ff6700;
    }
  }
}

.box-left {
  float: left;
  width: 234px;
  height: 614px;
  cursor: pointer;
  transition: all 0.3s;
  &:hover {
    transform: translateY(-1px);
    box-shadow: 5px 5px 20px #ccc;
  }
}

.box-right {
  float: left;
  width: 992px;
  height: 628px;
  .box-list {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    width: 100%;
    height: 100%;
    background: #f5f5f5;
  }
  .box-item {
    position: relative;
    margin: 0 0 14px 14px;
    padding: 20px 0;
    width: 234px;
    height: 260px;
    background: #fff;
    transition: all 0.3s;
    &:hover {
      transform: translateY(-1px);
      box-shadow: 5px 5px 20px #ccc;
    }
    .discount-label {
      position: absolute;
      top: 0;
      left: 50%;
      width: 64px;
      height: 20px;
      line-height: 20px;
      margin-left: -32px;
      font-size: 12px;
      text-align: center;
      color: #fff;
      z-index: 4;
      &.free {
        background-color: #ffac13;
      }
      &.new {
        background-color: #83c44e;
      }
      &.discount {
        background-color: #e53935;
      }
    }
    .old-price {
      color: #b0b0b0;
      text-decoration: line-through;
    }
    img {
      display: block;
      width: 160px;
      height: 160px;
      margin: 0 auto;
    }
    .box-title {
      font-size: 14px;
      text-align: center;
      color: #333;
      font-weight:normal;
    }
    .box-desc {
      margin: 0 10px 10px;
      height: 18px;
      font-size: 12px;
      text-align: center;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
      color: #b0b0b0;
    }
    .box-price {
      color: #ff6700;
      font-size: 14px;
      text-align: center;
    }
  }
}

</style>
