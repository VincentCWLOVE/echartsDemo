<template>
  <div class="echarts"></div>
</template>

<style scoped>
.echarts {
	margin: 30px auto;
  width: 600px;
  height: 400px;
}
</style>

<script>
import ECharts from "echarts"

export default {
	data () {
		return {
			chart : null
		}
	},
	//安装
	mounted() {

        this.chart = ECharts.init(document.querySelector('.echarts'));
        console.log(this.chart);
        this.chart.setOption({
	        title: { text: 'ECharts 入门示例' },
	    	tooltip: {},
	    	xAxis: {
	        	data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
	    	},
	    	yAxis: {},
	    	series: [{
	        	name: '销量',
	        	type: 'bar',
	        	data: [5, 20, 36, 10, 10, 20]
	    	}]
        });
    }

}

</script>