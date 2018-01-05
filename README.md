# MultiPlayer.js
*该播放器Web SDK让您可以在主流的桌面和移动端浏览器上播放hls协议的直播视频以及mp4、m3u8格式的点播视频。**

## Example

```js

function resize(){
	$("#video-container").css({height: ($("#video-container").width()*9/16)+"px"});
}
$(window).on("resize.demo", function(){
	resize();
});
resize();

var player = new MultiPlayer($("#video-container"), {
    server: 'vod',//live-直播、vod-点播
  	logo: "",//自定义logo 
  	title: "标题",//自定义title
  	speed: {//播放速率【直播中不会渲染】
      show: true,
      speedValue: [2.5, 2.0, 1.5, 1.0, 0.5],
  	},
  	poster: "", //默认封面
  	audioposter: "", //切换音频流后显示封面
  	controls: true, //是否显示控制栏
	urls: {//播放地址列表
		hlsUrl: {//直播 地址
			url: "http://xxxxxxx/index.m3u8",
			url_720: "http://xxxxxxx/index.m3u8",
			url_480: "http://xxxxxxx/index.m3u8",
			url_audio: "http://xxxxxxx_audio/index.m3u8"
		},
		vodUrl: {//点播
			// url: "http://xxxxxxx/index.m3u8",
			// url_720: "http://xxxxxxx/index.m3u8",
			// url_480: "http://xxxxxxx/index.m3u8",
			// url_audio: "http://xxxxxxx_audio/index.m3u8"
			url: "test.mp4",
			url_high: "test.mp4",
			url_720: "test.mp4",
			url_480: "test.mp4",
			url_1080: "test.mp4",
			url_audio: "test.mp4"
		}
	},
	startTime: null, //点播：设置开始播放时间， 单位：秒
	endTime: null, //点播：设置结束播放时间， 单位：秒
  	position: null //点播：续播位置， 单位：秒
});
player.on("ended", function(e){
	  console.log('停止播放');
});
player.on("timeupdate", function(event, data){
  console.log('播放实时进度心跳');
});
player.on("share", function(){
	console.log("自定义分享事件");
});

``` 
