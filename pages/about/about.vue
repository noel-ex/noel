<template>
	<view class="pages">
		<view class="initHeader initHeader--white">
			<view class="initHeader-wrapper">
				<view class="initHeader-back" @click="$tools.back(1)"></view>
			</view>
		</view>
		<view class="versionBox">
			<view class="versionBox-logo"><image src="../../static/about/icon-about-logo.png" mode="widthFix" /></view>
			<view class="versionBox-title">{{i18n.g_current_p}} {{ version }}</view>
			<view class="versionBox-info">
				{{i18n.about_info}}
			</view>
		</view>
		<view class="listBox">
			<view class="listBox-list" @click="$tools.jump('../about/about_privacyService')">
				<text class="listBox-list__lable"> {{i18n.g_service_privacy}} </text>
				<view class="listBox-list__arrow"><image src="../../static/public/icon-arrow-right-grey.png" mode="widthFix" /></view>
			</view>
			<view class="listBox-list" @click="$tools.jump('../about/about_privacyPolicy')">
				<text class="listBox-list__lable">{{i18n.g_policy_privacy}}</text>
				<view class="listBox-list__arrow"><image src="../../static/public/icon-arrow-right-grey.png" mode="widthFix" /></view>
			</view>
			<view class="listBox-list" @click="$tools.jump('../about/about_papelBlanco')">
				<text class="listBox-list__lable">{{i18n.g_project_introdution}}</text>
				<view class="listBox-list__arrow"><image src="../../static/public/icon-arrow-right-grey.png" mode="widthFix" /></view>
			</view>
			<view class="listBox-list">
				<text class="listBox-list__lable">{{i18n.g_version_diary}}</text>
				<view class="listBox-list__arrow"><image src="../../static/public/icon-arrow-right-grey.png" mode="widthFix" /></view>
			</view>
		</view>
		<!-- <view class="copyRight">
			Copyright © 2018 ConsenLabs
			<br />
			ALL right reserved
		</view> -->
	</view>
</template>

<script>
import version from '@/components/url.js';
export default {
	data() {
		return {
			version: version.version
		};
	},
	
	computed: {
		i18n() {
			return this.$t('message')
		}
	},
};
</script>

<style lang="scss" scoped>

.versionBox {
	padding: 30upx;
	@include flexCenterColumn;
	
	&-logo {
		width: 180upx;
		margin-bottom: 30upx;
		@include fullImage;
	}
	&-title {
		text-align: center;
		margin-bottom: 30upx;
		font-size: 24upx;
		color: #999999;
	}
	&-info {
		font-size: 24upx;
		color: #FFFFFF;
		text-indent: 2em;
	}
}

.listBox {
	padding: 30upx;
	&-list {
		font-size: 28upx;
		// border-bottom: 2upx solid #ececec;
		padding: 30upx 0;
		color: #FFFFFF;
		@include flexBetween;

		&__arrow {
			width: 14upx;
			@include fullImage;
		}
	}
}

.pages {
	.link {
		.li {
			display: flex;
			padding: 0 40upx;
			height: 100upx;
			border-bottom: 1upx solid #ececec;
			background-color: #fff;
			text {
				flex: 1;
				line-height: 100upx;
				font-size: 30upx;
				color: #666;
			}
			.ver {
				color: #666;
				font-size: 28upx;
				margin-right: 30upx;
				line-height: 100upx;
			}
			.spans {
				display: flex;
				width: 40upx;
				justify-content: center;
				align-items: center;
				image {
					width: 28upx;
				}
			}
		}
	}
	.copyRight {
		height: 160upx;
		text-align: center;
		padding: 40upx 40upx;
		// position:fixed;
		bottom: 0;
		left: 0;
		right: 0;
		font-size: 28upx;
		color: #999;
	}
}
</style>
