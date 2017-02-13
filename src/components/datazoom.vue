<template>
  <div class="datazoom"></div>
</template>

<style scoped>
.datazoom {
  width: 600px;
  height: 400px;
  margin: 30px auto;
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
        this.chart = ECharts.init(document.querySelector('.datazoom'));
        
        this.chart.setOption({
        	title : {text:"交互组件datazoom"},
	       	xAxis: {
		        type: 'value'
		    },
		    yAxis: {
		        type: 'value'
		    },
		    dataZoom: [
		        // {   // 这个dataZoom组件，默认控制x轴。
		        //     type: 'slider', // 这个 dataZoom 组件是 slider 型 dataZoom 组件
		        //     start: 10,      // 左边在 10% 的位置。
		        //     end: 60         // 右边在 60% 的位置。
		        // }
		        {
		            type: 'slider',
		            xAxisIndex: 0,
		            start: 10,
		            end: 60
		        },
		        {
		            type: 'inside',
		            xAxisIndex: 0,
		            start: 10,
		            end: 60
		        },
		        {
		            type: 'slider',
		            yAxisIndex: 0,
		            start: 30,
		            end: 80
		        },
		        {
		            type: 'inside',
		            yAxisIndex: 0,
		            start: 30,
		            end: 80
		        }
		    ],
		    series: [
		        {
		            type: 'scatter', // 这是个『散点图』
		            itemStyle: {
		                normal: {
		                    opacity: 0.8
		                }
		            },
		            symbolSize: function (val) {
		                return val[2] * 40;
		            },
		            data: [["14.616","7.241","0.896"],["3.958","5.701","0.955"],["2.768","8.971","0.669"],["9.051","9.710","0.171"],["14.046","4.182","0.536"],["12.295","1.429","0.962"],["4.417","8.167","0.113"],["0.492","4.771","0.785"],["7.632","2.605","0.645"],["14.242","5.042","0.368"]]
		        },
		        {
		            type: 'scatter', // 这是个『散点图』
		            itemStyle: {
		                normal: {
		                    opacity: 0.8,
		                    color:"blue"
		                }
		            },
		            symbolSize: function (val) {
		                return val[2] * 40;
		            },
		            data: [["15.616","8.241","1.896"],["4.958","7.701","1.955"],["3.768","10.971","2.669"],["9.051","9.710","0.171"],["14.046","4.182","0.536"],["12.295","1.429","0.962"],["4.417","8.167","0.113"],["0.492","4.771","0.785"],["7.632","2.605","0.645"],["14.242","5.042","0.368"]]
		        }
		    ]
        });
    }

}

</script>