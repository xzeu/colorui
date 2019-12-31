> ##  HdpUI 头部导航组件

## 组件说明
```
hdpHeader 用于完成自定义头部导航（您已经关闭了系统原生的导航）, 自动完成了沉浸式、小程序胶囊按钮躲避等工作;
```
## 组件属性
```
background:{type : String, default : "#F8F8F8"}// 背景颜色 : none代表空, 可以使用 linear-gradient() 进行渐变，使用 url 做背景图
height:{type : Number, default : 90} // 导航高度,单位 rpx
haveStatusBar{type : Boolean, default : true} // 是否自动处理从沉浸式
isSeize{type : Boolean, default : true} // 是否自动产生一个占位原生避免导航遮盖下面的元素
zIndex{type : Number, default : 99} // [ 新增 ] 层级
```
# uni-app模型下关闭原生导航

```
{
	"path" : "pages/layout/header",
	"style" : {
		"titleNView" : false,
		"bounce" : "none",
		"scrollIndicator" : "none",
		"navigationStyle" : "custom"
	}
}
```

## 演示代码

```
<template>
	<view>
		<!--  演示一个渐变背景，请根据项目实际需求自行改进  -->
		<graceHeader background="linear-gradient(to right, #B100FF 0%,#00B3FF 80%)">
			<view class="grace-header-body">
				<!-- 返回按钮 -->
				<view class="grace-header-icons grace-icons icon-arrow-left grace-white" @tap="goback"></view>
				<!-- 中间内容 -->
				<view class="grace-header-content-noflex">
					<graceSearch></graceSearch>
				</view>
				<!-- 设置按钮 -->
				<view class="grace-header-icons grace-icons icon-set grace-white" @tap="set"></view>
			</view>
		</graceHeader>
		<!-- 主体内容开始区域  -->
		<view>
			<view style="padding:50rpx; background:#F5F6F8;">
				主体内容.......
			</view>
		</view>
	</view>
</template>
<script>
import graceHeader from '../../graceUI/components/graceHeader.vue';
import graceSearch from '../../graceUI/components/graceSearch.vue';
export default {
    data() {
        return {}
    },
    methods: {
		goback : function(){
			uni.showToast({title:"您点击了返回按钮", icon: "none"});
			uni.navigateBack({});
		},
		set : function(){
			uni.showToast({title:"您点击了设置按钮", icon: "none"});
		} 
    },
    components:{
		graceHeader,
		graceSearch
    }
}
</script>
<style>
</style>
```
