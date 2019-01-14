<template>
  <div class="wrap">
    <h1>购物商城</h1>

    <div>
      <h2>商品列表</h2>
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
          title: "商品1",
          desc: "描述111111111111111111111",
          cover: "./static/img/social-media.png",
          price: 100,
          stock: 99
        },
        {
          title: "商品2",
          desc: "描述2222222222222222222222222",
          cover: "./static/img/social-media.png",
          price: 1040,
          stock: 299
        },
        {
          title: "商品3",
          desc: "描述33333333333333333333333333",
          cover: "./static/img/social-media.png",
          price: 1060,
          stock: 22
        },

        {
          title: "商品4",
          desc: "描述444444444444444444444444444",
          cover: "./static/img/social-media.png",
          price: 100,
          stock: 33
        },

        {
          title: "商品5",
          desc: "描述55555555555555555555555555555",
          cover: "./static/img/social-media.png",
          price: 1100,
          stock: 199
        },

        {
          title: "商品6",
          desc: "描述6666666666666666666666666666",
          cover: "./static/img/social-media.png",
          price: 1000,
          stock: 540
        },

        {
          title: "商品7",
          desc: "描述7777777777777777777777777",
          cover: "./static/img/social-media.png",
          price: 299,
          stock: 199
        }
      ],
      shoppingCart: [
        {
          title: ""
        }
      ]
    };
  },
  mounted() {
    setTimeout(() => {
      this.name = "yy";

      // document.getElementById("app").innerHTML = "hello,yy";
    }, 2000);
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
}
</style>
