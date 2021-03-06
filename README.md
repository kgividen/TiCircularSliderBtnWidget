# TiCircularSliderBtnWidget
A circular slider with button for Titanium

# TiCircularSliderBtnWidget [![Titanium](http://www-static.appcelerator.com/badges/titanium-git-badge-sq.png)](http://www.appcelerator.com/titanium/)

<img src="sample.png" />

## About
TiCircularSliderBtnWidget is an Alloy Widget for Titanium for iOS and Android. It uses
[kgividen fork Of TiCircularSlider](https://github.com/kgividen/TiCircularSlider) based on [TiCircularSlider](https://github.com/mpociot/TiCircularSlider).  I'll create a pull request for that soon.

TiCircularSlider uses the native modules
[EFCircularSlider](https://github.com/eliotfowler/EFCircularSlider) on iOS and [HoloCircleSeekBar](https://github.com/JesusM/HoloCircleSeekBar) on Android. 

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

```
"#btn" : {
	name:'Blah',
	top:'20',
	width: 100,
	height: 100,
	filledColor:'#31B3E7',
	unfilledColor: '#898989',
	btnOnColor: '#31B3E7',
	btnOffColor: '#898989',
	currentValueOnColor: '#31B3E7',
	currentValueOffColor: '#898989',
	btnLabelOnColor: 'white',
	btnLabelOffColor: 'white',
	buttonNameFont: {
       		fontSize : "8"
	}
}

"#btn2" : {
	name: 'Button2',
	top:'150',
	width: 50,
	height: 50
}

```

or you can do it in the controller:

```
var style = {
	width: 100,
	height: 100,
	filledColor:'#31B3E7',
	unfilledColor: '#898989',
	btnOnColor: '#31B3E7',
	btnOffColor: '#898989',
	currentValueOnColor: '#31B3E7',
	currentValueOffColor: '#898989',
	btnLabelOnColor: 'white',
	btnLabelOffColor: 'white',
	buttonNameFont: {
       	fontSize : "8"
	}
};
blah.btn = Alloy.createWidget('TiCircularSliderBtnWidget',style).getView();

```
