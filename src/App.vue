<template>
	<div class="layout" :class="{'layout-hide-text': spanLeft < 5}">
		<Row type="flex">
            <Col :span="spanLeft" class="layout-menu-left">
                <Menu active-name="1" theme="dark" width="auto">
                    <div class="layout-logo-left"></div>
                    <MenuItem name="1">
                        <Icon type="ios-navigate" :size="iconSize"></Icon>
                        <span class="layout-text">选项 1</span>
                    </MenuItem>
                    <MenuItem name="2">
                        <Icon type="ios-keypad" :size="iconSize"></Icon>
                        <span class="layout-text">选项 2</span>
                    </MenuItem>
                    <MenuItem name="3">
                        <Icon type="ios-analytics" :size="iconSize"></Icon>
                        <span class="layout-text">选项 3</span>
                    </MenuItem>
                </Menu>
            </Col>
            <Col :span="spanRight">
                <div class="layout-header">
                    <Button type="text" @click="toggleClick">
                        <Icon type="navicon" size="32"></Icon>
                    </Button>
                </div>
                <div class="layout-breadcrumb">
                    <Breadcrumb>
                        <BreadcrumbItem href="#">首页</BreadcrumbItem>
                        <BreadcrumbItem href="#">应用中心</BreadcrumbItem>
                        <BreadcrumbItem>某应用</BreadcrumbItem>
                    </Breadcrumb>
                </div>
                <div class="layout-content">
                    <div class="layout-content-main"></div>
                </div>
                <div class="layout-copy">
                    2011-2016 &copy; TalkingData
                </div>
            </Col>
        </Row>
	</div>
</template>

<script>
import{
	Row,
	Col,
	Menu,
	MenuItem,
	Button,
	Breadcrumb,
	BreadcrumbItem,
} from 'iView'
export default {
	name: 'index',
	data () {
		return {
			spanLeft: 5,
			spanRight: 19,
		}
	},
	computed: {
		iconSize () {
			return this.spanLeft === 5 ? 14 : 24;
		}
	},
	components: {
		Row,
		Col,
		Menu,
		MenuItem,
		Button,
		Breadcrumb,
		BreadcrumbItem,
	},
	methods: {
		toggleClick () {
			if (this.spanLeft === 5) {
				this.spanLeft = 2;
				this.spanRight = 22;
			} else {
				this.spanLeft = 5;
				this.spanRight = 19;
			}
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss'>
@import './assets/common.scss';

.layout{
	border: 1px solid #d7dde4;
	background: #f5f7f9;
	position: relative;
	border-radius: 4px;
    overflow: hidden;
    height: 100%;

    .ivu-row-flex{
        height: 100%;
    }

	.layout-breadcrumb{
        padding: 10px 15px 0;
    }
    .layout-content{
        min-height: 490px;
        margin: 15px;
        overflow: hidden;
        background: #fff;
        border-radius: 4px;
    }
    .layout-content-main{
        padding: 10px;
    }
    .layout-copy{
        text-align: center;
        padding: 10px 0 20px;
        color: #9ea7b4;
    }
    .layout-menu-left{
        background: #464c5b;
    }
    .layout-header{
        height: 60px;
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
    .layout-logo-left{
        width: 90%;
        height: 30px;
        background: #5b6270;
        border-radius: 3px;
        margin: 15px auto;
    }
    .layout-ceiling-main a{
        color: #9ba7b5;
    }
    .layout-hide-text .layout-text{
        display: none;
    }
    .ivu-col{
        transition: width .2s ease-in-out;
    }
}
</style>
