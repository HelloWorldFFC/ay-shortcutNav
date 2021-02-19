
## 前言
简介：首页快捷键，类似支付宝、美团、饿了么首页快捷键，传入数据即可使用，可传背景色，一行展示个数等

## 有疑问
微信搜索“慢慢向好”小程序，找客服反馈，相应问题。
				  

## 素材
[图片资源](https://pixabay.com)
 
## 开始使用
下载源码解压，复制`/components` 下的组件至项目根目录的 `/components` 文件夹下


`index.vue`的`script`加入如下部分：
```
import tiled from '@/components/ay-shortcutNav/tiled.vue';
import shortcutNav from '@/components/ay-shortcutNav/shortcutNav.vue';
	export default {
		components: {
			shortcutNav,
			tiled,
		},
		data() {
			return {
				navbackgroundColor: '#fff',
				themeColor: '#33CCCC',
				shortcutNavList: [{
					img: 'https://cdn.pixabay.com/photo/2020/01/01/18/51/bottle-of-sparkling-wine-4734176__340.jpg',
					name: '立人',
					key: '立人',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/10/04/09/57/feather-5625806__340.jpg',
					name: '立德',
					key: '立德',
				}, {
					img: 'https://cdn.pixabay.com/photo/2019/11/19/12/04/daisy-4637276__340.jpg',
					name: '立言',
					key: '立言',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/11/16/16/05/hoverfly-5749361__340.jpg',
					name: '立行',
					key: '立行',
				}, ],
				shortcutNavList_two: [{
					img: 'https://cdn.pixabay.com/photo/2020/03/23/08/37/taiwan-4959896__340.jpg',
					name: '富强民主',
					key: '富强民主',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/05/07/17/48/finch-5142472__340.jpg',
					name: '文明和谐',
					key: '文明和谐',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/05/23/14/58/nature-5209956__340.jpg',
					name: '自由平等',
					key: '自由平等',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/09/07/21/53/flowers-5552966__340.jpg',
					name: '公正法治',
					key: '公正法治',
				}, {
					img: 'https://cdn.pixabay.com/photo/2019/11/18/02/41/autumn-leaves-4633854__340.jpg',
					name: '爱国敬业',
					key: '爱国敬业',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/10/30/11/23/chrysanthemums-5698303__340.jpg',
					name: ' 诚信友善',
					key: ' 诚信友善',
				}, {
					img: 'https://cdn.pixabay.com/photo/2020/11/06/08/52/leaves-5717222__340.jpg',
					name: '社会主义',
					key: '社会主义',
				}, {
					img: 'https://cdn.pixabay.com/photo/2018/08/09/22/44/wasp-3595688__340.jpg',
					name: '核心价值观',
					key: '核心价值观',
				}, ],
			}
		},
		onLoad() {
			let that = this;

		},

		methods: {
			toDetailPage(e) {
				let list = e.list;
				let idx = e.curIndex;
				let list_img = [];
				list.forEach(item => {
					list_img.push(item.img)
				})
				if (list_img && list_img.length > 0) {
					uni.previewImage({
						current: list_img[idx],
						// 传 Number H5端出现不兼容 
						urls: list_img,
						indicator: "number",
						loop: true,
					});
				}
			},

		}
	}
	
```


`index.vue`的`template`加入如下部分：(三选一)
```
 <view class="content">
 	<shortcutNav :list="shortcutNavList" :hengNumber="4" @toDetailPage="toDetailPage"></shortcutNav>
 		<view class="NavBox marginBottom-Theme">
 			<shortcutNav style="padding: 80upx 20upx 20upx 20upx;" :list="shortcutNavList_two" :hengNumber="4" :boxshadow="false"
 			 :borderRadius="false" @toDetailPage="toDetailPage"></shortcutNav>
 		</view>
 
 		<shortcutNav :list="shortcutNavList.slice(0,3)" :hengNumber="3" :backgroundColor="navbackgroundColor" @toDetailPage="toDetailPage"></shortcutNav>
 
 </view>

```

或
`index.vue`的`template`加入如下部分：(二选一)
```
 <view class="content">
 	<view class="marginBottom-Theme">
 		<tiled :list="shortcutNavList" :hengNumber="2" @toDetailPage="toDetailPage" img_last="lgg"></tiled>
 	</view>
 	<tiled :list="shortcutNavList" :hengNumber="3" @toDetailPage="toDetailPage" backgroundColor="#BA55D3" nameColor="#fff"
 	 img_last="lg"></tiled>
 
 </view>

```


`index.vue`的`style`加入如下部分：
```
 <style lang="scss">
 	.NavBox {
 		width: 94%;
 		margin: 0upx 20upx;
 	}
 	.marginBottom-Theme {
 		margin-bottom: 20upx;
 	}
 </style>

```




页面`App.vue` 加上样式
```

<style lang="scss"> /*每个页面公共css */ view, scroll-view, swiper, swiper-item, cover-view, cover-ima<style lang="scss">
	 view,
	 scroll-view,
	 swiper,
	 swiper-item,
	 cover-view,
	 cover-image,
	 icon,
	 text,
	 rich-text,
	 progress,
	 button,
	 checkbox,
	 form,
	 input,
	 label,
	 radio,
	 slider,
	 switch,
	 textarea,
	 navigator,
	 audio,
	 camera,
	 image,
	 video {
	 	box-sizing: border-box;
	 }
	 
	 /* 骨架屏替代方案 */
	 .Skeleton {
	 	background: #f3f3f3;
	 	padding: 20upx 0;
	 	border-radius: 8upx;
	 }
	 
	 /* 图片载入替代方案 */
	 .image-wrapper {
	 	font-size: 0;
	 	background: #f3f3f3;
	 	border-radius: 4px;
	 
	 	image {
	 		width: 100%;
	 		height: 100%;
	 		transition: .6s;
	 		opacity: 0;
	 
	 		&.loaded {
	 			opacity: 1;
	 		}
	 	}
	 }
	 
	 .clamp {
	 	overflow: hidden;
	 	text-overflow: ellipsis;
	 	white-space: nowrap;
	 	display: block;
	 }
	 
	 .common-hover {
	 	background: #f5f5f5;
	 }
	 
	 /*边框*/
	 .b-b:after,
	 .b-t:after {
	 	position: absolute;
	 	z-index: 3;
	 	left: 0;
	 	right: 0;
	 	height: 0;
	 	content: '';
	 	transform: scaleY(.5);
	 	border-bottom: 1px solid $uni-border-color;
	 }
	 
	 .b-b:after {
	 	bottom: 0;
	 }
	 
	 .b-t:after {
	 	top: 0;
	 }
	 
	 /* button样式改写 */
	 uni-button,
	 button {
	 	height: 80upx;
	 	line-height: 80upx;
	 	font-size: $uni-font-size-lg + 2rpx;
	 	font-weight: normal;
	 
	 	&.no-border:before,
	 	&.no-border:after {
	 		border: 0;
	 	}
	 }
	 
	 uni-button[type=default],
	 button[type=default] {
	 	color: #303133;
	 }
	 
	 /* input 样式 */
	 .input-placeholder {
	 	color: #999999;
	 }
	 
	 .placeholder {
	 	color: #999999;
	 }
</style>

```

 ## 说明
因调试上次的链接没有图片了，故换了链接