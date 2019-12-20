<template>
  <div class="hello">
    <div id="c1"></div>
  </div>
</template>

<script>
import G2 from '@antv/g2';
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data(){
    return {
      list: [
      { genre: "Sports", sold: 275 },
      { genre: "Strategy", sold: 115 },
      { genre: "Action", sold: 120 },
      { genre: "Shooter", sold: 350 },
      { genre: "Other", sold: 150 }
     ]
    }
  },
  mounted() {
    const chart = new G2.Chart({
      container: "c1", // 指定图表容器 ID
      forceFit: true,
      width: 600, // 指定图表宽度
      height:300 ,// 指定图表高度
      padding: [ 20, 20, 95, 80 ], // 上，右，下，左
      background:{color:'pink'},
    });
    // Step 2: 载入数据源
    chart.source(this.list);
    chart.interval().position("genre*sold").color("genre");
    // Step 4: 渲染图表
    chart.render();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='less' scoped>

</style>
