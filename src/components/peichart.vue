<template>
  <div class="peicharts"></div>
</template>

<style scoped>
.peicharts {
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
        this.chart = ECharts.init(document.querySelector('.peicharts'));
        
        this.chart.setOption({
        	title : {text:"饼状图"},
	       	series : [
		        {
		            name: '访问来源',
		            type: 'pie',
		            radius: '55%',
		            data:[
		                {value:400, name:'搜索引擎'},
		                {value:335, name:'直接访问'},
		                {value:310, name:'邮件营销'},
		                {value:274, name:'联盟广告'},
		                {value:235, name:'视频广告'}
		            ]
		        }
		    ],
		    roseType: 'angle',
		    itemStyle: {
			    normal: {
			        // 阴影的大小
			        shadowBlur: 200,
			        // 阴影水平方向上的偏移
			        shadowOffsetX: 0,
			        // 阴影垂直方向上的偏移
			        shadowOffsetY: 0,
			        // 阴影颜色
			        shadowColor: 'rgba(0, 0, 0, 0.5)'
			    },
			        emphasis: {
			        shadowBlur: 200,
			        shadowColor: 'rgba(0, 0, 0, 0.5)'
			    }
			},
			visualMap: {
			    // 不显示 visualMap 组件，只用于明暗度的映射
			    show: false,
			    // 映射的最小值为 80
			    min: 80,
			    // 映射的最大值为 600
			    max: 600,
			    inRange: {
			        // 明暗度的范围是 0 到 1
			        colorLightness: [0, 1]
			    }
			}
        });
    }

}

</script>