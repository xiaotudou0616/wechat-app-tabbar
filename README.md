# wechat-app-tabbar
##微信小程序 自定义tabbar

![tabbar](https://github.com/songzeng2016/wechat-app-tabbar/raw/master/images/GIF.gif)   

首先创建一个wxml模板
```
<template name="tabbar">
    <view class="tabbar_box" style="background-color:{{tabbar.backgroundColor}}; border-top-color:{{tabbar.borderStyle}}; {{tabbar.position == 'top' ? 'top:0' : 'bottom:0'}}">
        <block wx:for="{{tabbar.list}}" wx:for-item="item" wx:key="index">
            <navigator class="tabbar_nav" url="{{item.pagePath}}" style="width:{{1/tabbar.list.length*100}}%; color:{{item.selected ? tabbar.selectedColor : tabbar.color}}" open-type="redirect">
                <image class="tabbar_icon" src="{{item.selected ? item.selectedIconPath : item.iconPath}}"></image>
                <text>{{item.text}}</text>
            </navigator>
        </block>
    </view>
</template>
```
