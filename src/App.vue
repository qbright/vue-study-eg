<template>
  <div class="wrap">
    <h1>购物商城</h1>

    <div>
      <h2>商品列表</h2>
      <ul class="commodity-list">
        <li v-for="(item ) in commodityList" :key="item.id" class="list-item">
          <p>名称: {{item.title}}</p>
          <p>描述: {{item.desc}}</p>
          <p>价格: {{item.price}}</p>
          <p>库存: {{item.stock}}</p>
          <p>
            <button @click="subtract(item)">减一</button>
            <input type="text" v-model="item.buy">
            <button @click="plus(item)">加一</button>
          </p>
        </li>
      </ul>
    </div>
    <div>
      <h2>已购商品</h2>
      <ul>
        <li v-for="(item) in boughtList" :key="item.id">{{item.title}} --- 买了 : {{item.buy}}</li>
      </ul>
    </div>
    <div v-if="total">
      <h2>总价 : {{total}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      commodityList: [
        {
          id: 1,
          title: "商品1",
          desc: "描述111",
          price: 100,
          stock: 99,
          buy: 0
        },
        {
          id: 2,
          title: "商品2",
          desc: "描述222",
          price: 1040,
          stock: 299,
          buy: 0
        },
        {
          id: 3,
          title: "商品3",
          desc: "描述333",
          price: 1060,
          stock: 22,
          buy: 0
        },

        {
          id: 4,
          title: "商品4",
          desc: "描述444",
          price: 100,
          stock: 33,
          buy: 0
        },

        {
          id: 5,
          title: "商品5",
          desc: "描述555",
          price: 1100,
          stock: 199,
          buy: 0
        },

        {
          id: 6,
          title: "商品6",
          desc: "描述666",
          price: 1000,
          stock: 540,
          buy: 0
        },

        {
          id: 7,
          title: "商品7",
          desc: "描述777",
          price: 299,
          stock: 199,
          buy: 0
        }
      ],
      shoppingCart: {}
    };
  },
  mounted() {
    setTimeout(() => {
      this.name = "yy";

      // document.getElementById("app").innerHTML = "hello,yy";
    }, 2000);
  },
  computed: {
    boughtList() {
      return this.commodityList.filter(item => {
        return item.buy > 0;
      });
    },
    total() {
      if (!this.boughtList.length) {
        return 0;
      }
      return this.boughtList.reduce(
        (sum, curr) => sum + curr.price * curr.buy,
        0
      );
    }
  },
  methods: {
    subtract(item) {
      if (item.buy <= 0) {
        return;
      }

      item.buy--;
      item.stock++;
    },
    plus(item) {
      if (item.stock <= 0) {
        return;
      }

      item.buy++;
      item.stock--;
    },
    addcart(item) {
      if (!this.shoppingCart[item.id]) {
        this.shoppingCart[item.id] = {
          title: item.title,
          desc: item.desc,
          price: item.price
        };
      }
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.wrap {
  padding: 20px 100px;
  padding-bottom: 100px;
}

.commodity-list {
  list-style-type: none;
  overflow: hidden;
}

.list-item {
  float: left;
  border: 1px solid #d2d2d2;
  padding: 10px;
  width: 350px;
  margin: 10px;
  border-radius: 5px;
}
</style>
