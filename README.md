#### 全局映入
      main.js
            import nineCard from './components/nineCard/nineCard.vue'
            Vue.component('nine-view',nineCard);
#### 全局映入
        xxx.vue
         import mpvueEcharts from '@/components/mpvue-echarts/src/echarts.vue';
#### 使用
      <nine-view :data="menuList" :styleData="styleData"></nine-view>
#### 入参说明
```javascript
styleData:{
    height:"275",//单个格子高度
    imgStyle:{//图标宽高
      width:"130",
      height:"130"
    }
  },
  //格子list
  menuList:[
    {
      path:'../jiananSys/jiananSys',//跳转路由路径
      permissionCode:"1",//权限编码
      imageUrl:"../../static/images/itemcon.png",//图标url
      name:"建安系统"//名称
    },
    {
      path:'../safeManage/safeManage',
      permissionCode:"6",
      imageUrl:"../../static/images/nine9.png",
      name:"安全管理"
    },
    {
      path:'',
      permissionCode:"7",
      imageUrl:"../../static/images/nine8.png",
      name:"环保监控管理"
    },
    {
      path:'',
      permissionCode:"4",
      imageUrl:"../../static/images/nine2.png",
      name:"文档管理"
    }
   ]
```
#### 取权限匹配判断
```javascript
matchPermission = (value) => {
	var permissionData = [];
	var permission=[];
  //uni.getStorageSync("loginStorageData").permission 接收接口返回的所有权限列表
	uni.getStorageSync("loginStorageData").permission.forEach(function(item,index){
		permissionData.push(item.permissionCode);
	});
	[app中所需的所有权限code].forEach(function(item,index){
		if(permissionData.includes(item)){
			permission.push(item);
		}
	});
	return permission.includes(value+"");
}
```
