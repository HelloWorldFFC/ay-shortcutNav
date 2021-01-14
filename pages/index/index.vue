<template>
	<view class="content">
		<shortcutNav :list="shortcutNavList" :hengNumber="4" @toDetailPage="toDetailPage"></shortcutNav>
			<view class="NavBox marginBottom-Theme">
				<shortcutNav style="padding: 80upx 20upx 20upx 20upx;" :list="shortcutNavList_two" :hengNumber="4" :boxshadow="false"
				 :borderRadius="false" @toDetailPage="toDetailPage"></shortcutNav>
			</view>

			<shortcutNav :list="shortcutNavList.slice(0,3)" :hengNumber="3" :backgroundColor="navbackgroundColor" @toDetailPage="toDetailPage"></shortcutNav>

	</view>
</template>

<script>
	import shortcutNav from '@/components/ay-shortcutNav/shortcutNav.vue';
	export default {
		components: {
			shortcutNav,

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
</script>

<style lang="scss">
	.NavBox {
		width: 94%;
		margin: 0upx 20upx;
	}
	.marginBottom-Theme {
		margin-bottom: 20upx;
	}
</style>
