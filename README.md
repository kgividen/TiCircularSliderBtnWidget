# TiCircularSliderBtnWidget
A circular slider with button for Titanium

# TiCircularSliderBtnWidget [![Titanium](http://www-static.appcelerator.com/badges/titanium-git-badge-sq.png)](http://www.appcelerator.com/titanium/)

## About
TiCircularSliderBtnWidget is an Alloy Widget for Titanium for iOS and (soon to be Android). It uses
[TiCircularSlider](https://github.com/mpociot/TiCircularSlider).

TiCircularSlider uses the native modules
[EFCircularSlider](https://github.com/eliotfowler/EFCircularSlider) on iOS and [CircularSeekBar](https://github.com/RaghavSood/AndroidCircularSeekBar) on Android. 

## Quick Start

### Installation
Install the [TiCircularSlider](https://github.com/mpociot/TiCircularSlider) module.
Download the latest distribution ZIP-file and consult the [Titanium Documentation](http://docs.appcelerator.com/titanium/latest/#!/guide/Using_a_Module) on how install it, or simply use the [gitTio CLI](http://gitt.io/cli):

Download and install the TiCircularSliderBtnWidget

### Usage
```javascript
var args = arguments[0] || {};

$.btn.onClick(function (e) {
	Ti.API.info("onClick btn1 E: " + JSON.stringify(e));
});

$.btn2.onClick(function (e) {
	Ti.API.info("onClick btn2 E: " + JSON.stringify(e));
});

$.btn.onTouchEnd(function (e) {
	Ti.API.info("touchend E: " + JSON.stringify(e));
});

$.btn2.onTouchEnd(function (e) {
	Ti.API.info("touchend E: " + JSON.stringify(e));
});


$.win.addEventListener("open", function() {
    $.btn.setBtnValue(10); //TODO For some reason when this is set we can't drag the slider initially...we have to click then drag it so this is an issue.
    $.btn2.setBtnValue(20);
});
```

```xml
   <Alloy>
       <Window id="win" backgroundColor="white">
           <Widget id="btn" src="btnCircularSlider"/>
           <Widget id="btn2" top="150" src="btnCircularSlider"/>
       </Window>
   </Alloy>
```
