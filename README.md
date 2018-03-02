# 高德地图

- `setCity(city:String)`设置查询城市，支持cityname（中文或中文全拼）、citycode、adcode

- `getCenter()`获取当前Bounds的中心点经纬度坐标。

- `setZoom()`设置地图显示的缩放级别，在PC上，参数zoom可设范围：[3,18]；在移动端：参数zoom可设范围：[3,19]

- `getZoom()`获取当前地图缩放级别,在PC上，默认取值范围为[3,18]；在移动设备上，默认取值范围为[3-19];3D地图会返回浮点数，2D视图为整数。（3D地图自V1.4.0开始支持）

- 加载一个插件`plugin`
```
AMap.plugin(['AMap.ToolBar', 'AMap.AdvancedInfoWindow'], function () {
    //创建并添加工具条控件
    var toolBar = new AMap.ToolBar();
    map.addControl(toolBar);
    //创建高级信息窗体并在指定位置打开
    var infowindow = new AMap.AdvancedInfoWindow({
        content: '<div class="info-title">高德地图</div><div class="info-content">' +
            '<img src="http://webapi.amap.com/images/amap.jpg">' +
            '高德是中国领先的数字地图内容、导航和位置服务解决方案提供商。<br>' +
            '<a target="_blank" href="http://mobile.amap.com/">点击下载高德地图</a></div>',
        offset: new AMap.Pixel(0, -30)
    });
    infowindow.open(map, [116.480983, 39.989628]);
});
```

- 监听地图事件`dragend`停止拖拽地图时触发。如地图有拖拽缓动效果，则在拽停止，缓动开始前触发

- `zoomIn()`地图放大一级显示

- `zoomOut()`地图缩小一级显示