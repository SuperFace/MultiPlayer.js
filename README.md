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
  	speed: {
      show: true,
      speedValue: [2.5, 2.0, 1.5, 1.0, 0.5],
  	},
  	poster: "",
  	audioposter: "",
  	controls: true,
  	bigPlayButton: true,
	urls: {
		hlsUrl: {
			url: "http://xxxxxxx/index.m3u8",
			url_720: "http://xxxxxxx/index.m3u8",
			url_480: "http://xxxxxxx/index.m3u8",
			url_audio: "http://xxxxxxx_audio/index.m3u8"
		},
		vodUrl: {	
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
	startTime: null,
	endTime: null,
  	position: null
});
player.on("ended", function(e){
	  
});
player.on("timeupdate", function(event, data){
  
});
player.on("share", function(){
	console.log(99);
});

``` 
