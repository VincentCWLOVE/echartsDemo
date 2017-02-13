<template>
  <div class="asynchronus"></div>
</template>

<style scoped>
.asynchronus {
	margin: 30px auto;
  width: 600px;
  height: 400px;
}
</style>

<script>
import ECharts from "echarts"
import $ from 'jquery'

console.log($);

export default {
	data () {
		return {
			chart : null
		}
	},
	//安装
	mounted() {
        this.chart = ECharts.init(document.querySelector('.asynchronus'));
        
        this.chart.setOption({
	       	title: { text: 'ECharts jquery异步ajax请求' },
	    	tooltip: {},
	    	xAxis: {
	        	data: []
	    	},
	    	yAxis: {},
	    	series: [{
	        	name: '销量',
	        	type: 'bar',
	        	data: []
	    	}]
        });
        this.chart.showLoading();

  //       $.get("你的url").done(function (data) {
  //       	this.chart.hideLoading();
		//     // 填入数据
		//     this.chart.setOption({
		//         xAxis: {
		//             data: data.categories
		//         },
		//         series: [{
		//             // 根据名字对应到相应的系列
		//             name: '销量',
		//             data: data.data
		//         }]
		//     });
		// });
    }

}

</script>