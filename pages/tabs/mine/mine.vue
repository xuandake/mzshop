<template>
	<view>
		<user-card :userinfo='userinfo' :expand="expand"></user-card>
		<grid :nav='nav'></grid>
		<uni-list>
			<uni-list-item title="地址管理" @click='goAddress'></uni-list-item>
			<uni-list-item title="账号管理"></uni-list-item>
			<uni-list-item title="客服管理"></uni-list-item>
			<uni-list-item title="关于"></uni-list-item>
		</uni-list>
	</view>
</template>

<script>
	import userCard from '@/components/mine/user-card.vue'
	import grid from '@/components/common/grid.vue'
	import uniList from '@/components/mine/uni-list.vue'
	import uniListItem from '@/components/mine/uni-list-item.vue'
	import mockData from '@/data/mine.js'
	export default {
		components: {
			userCard,
			grid,
			uniList,
			uniListItem
		},
		data() {
			return {
				userinfo: {},
				expand: [],
				nav: []
			}
		},
		methods: {
			goAddress() {
				this.$jump('/pages/address/address-list/address-list')
			}
		},
		onLoad() {
			this.userinfo = mockData.userInfo;
			this.expand = mockData.walletInfo;
			this.nav = mockData.nav
		}
	}
</script>

<style>

</style>
