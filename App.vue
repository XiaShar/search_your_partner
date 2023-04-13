<script>
	export default {
		onLaunch: function() {
			console.warn('当前组件仅支持 uni_modules 目录结构 ，请升级 HBuilderX 到 3.1.0 版本以上！')
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@import '@/uni_modules/uni-scss/index.scss';
	/* #ifndef APP-NVUE */
	@import '@/static/customicons.css';

	// 设置整个项目的背景色
	page {
		background-color: #f5f5f5;
	}

	/* #endif */
	.example-info {
		font-size: 14px;
		color: #333;
		padding: 10px;
	}

	/* CDN 服务仅供平台体验和调试使用，平台不承诺服务的稳定性，企业客户需下载字体包自行发布使用并做好备份。 */
	@font-face {
		font-family: "仓耳渔阳体 W01";
		font-weight: 400;
		src: url("//at.alicdn.com/wf/webfont/NvHjKPz9AuKF/xcDsi5Cj6PY9.woff2") format("woff2"),
			url("//at.alicdn.com/wf/webfont/NvHjKPz9AuKF/vw1Z1E6y4cxS.woff") format("woff");
		font-display: swap;
	}
	
	/* CDN 服务仅供平台体验和调试使用，平台不承诺服务的稳定性，企业客户需下载字体包自行发布使用并做好备份。 */
	@font-face {
	  font-family: "得意黑";font-weight: 100;src: url("//at.alicdn.com/wf/webfont/NvHjKPz9AuKF/hzVOE5EAKnED.woff2") format("woff2"),
	  url("//at.alicdn.com/wf/webfont/NvHjKPz9AuKF/ldtNCOSexza0.woff") format("woff");
	  font-display: swap;
	}
</style>