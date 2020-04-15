<template>
  <div class="index-wrapper">
    <div class="index-left">
      <!-- 全部产品 -->
      <div class="index-left-block">
        <h2>全部产品</h2>
        <template v-for="product in productList">
          <h3>{{ product.title }}</h3>
          <ul>
            <li v-for="item in product.list">
                <a v-bind:href="item.url">{{ item.title }}</a>
            </li>
          </ul>
          <div class="hr"></div>
        </template>
      </div>
      <!-- 最新消息 -->
      <div class="index-left-block lastest-news">
        <h2>最新消息</h2>
        <ul>
          <li>ddd</li>
        </ul>
      </div>
    </div>
    <div class="index-right">
      <div style="margin:0 auto;width:700px;height:300px;background:red;">将来使用组件代替</div>
      <div class="index-boader-list">
        <div class="index-boader-item">
          <h2>第1个</h2>
          <p>第1个商品描述</p>
          <div class="index-boader-button">立即购买</div>
        </div>
        <div class="index-boader-item">
          <h2>第2个</h2>
          <p>第2个商品描述</p>
          <div class="index-boader-button">立即购买</div>
        </div>
        <div class="index-boader-item">
          <h2>第3个</h2>
          <p>第3个商品描述</p>
          <div class="index-boader-button">立即购买</div>
        </div>
        <div class="index-boader-item">
          <h2>第4个</h2>
          <p>第4个商品描述</p>
          <div class="index-boader-button">立即购买</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productList: {
        pc: {
          title: "PC产品",
          list: [
            {
              title: "数据统计",
              url: "http://starcraft.com"
            },
            {
              title: "数据预测",
              url: "http://warcraft.com"
            },
            {
              title: "流量分析",
              url: "http://overwatch.com",
              hot: true
            },
            {
              title: "广告发布",
              url: "http://hearstone.com"
            }
          ]
        },
        app: {
          title: "手机应用类",
          list: [
            {
              title: "91助手",
              url: "http://weixin.com"
            },
            {
              title: "产品助手",
              url: "http://weixin.com"
            },
            {
              title: "智能地图",
              url: "http://maps.com"
            },
            {
              title: "语音助手",
              url: "http://phone.com"
            }
          ]
        }
      }
    };
  }
};
</script>

<style scoped>
.index-wrapper {
  display: flex;
}
.index-left {
  width: 30%;
}
.index-right {
  width: 70%;
}
.index-left-block {
  margin: 15px;
  background: #ffffff;
  border-radius: 10px;
  box-shadow: 0 0 1px #dddddd;
}
.index-left-block .hr {
  border-bottom: 1px solid black;
  margin: 20px 0;
}
.index-left-block h2 {
  background: #4fc08d;
  color: #ffffff;
  padding: 10px 15px;
  margin-bottom: 20px;
}
.index-left-block h3 {
  color: #222;
  font-weight: bolder;
  padding: 0 15px 5px 15px;
}
.index-left-block ul {
  padding: 10px 15px;
}
.index-left-block li {
  padding: 5px;
}
.index-boader-list {
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
  justify-content: center;
}
.index-boader-item {
  width: 30%;
  height: 125px;
  padding-left: 120px;
  background: #ffffff;
  margin-right: 1%;
  box-shadow: 0 0 1px #ddd;
  margin-bottom: 20px;
  border-radius: 0 0 10px 10px;
}
</style>