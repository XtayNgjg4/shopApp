<script>
export default {
	onLaunch: function() {
		uni.setTabBarBadge({
			index: 2,
			text: '1'
		});
	}
};
</script>
<style lang="scss">
//#ifndef APP-PLUS-NVUE
@import 'components/colorui/icon.css';
//#endif
//#ifndef APP-PLUS-NVUE
.clearfix::before,
.clearfix::after {
	content: '';
	display: table;
	clear: both;
}
//#endif
.container {
	background-color: #f0f2f5;
	overflow: hidden;
}

//#ifndef APP-PLUS-NVUE
.fl {
	float: left;
}
.fr {
	float: right;
}
//#endif
//#ifndef APP-PLUS-NVUE
page,
view {
	font-family: PingFangSC-Regular;
}
//#endif
view {
	//#ifndef APP-PLUS-NVUE
	box-sizing: border-box;
	//#endif
}

//#ifndef APP-PLUS-NVUE
button {
	&.no-border:before,
	&.no-border:after {
		border: 0;
	}
}
//#endif
</style>
