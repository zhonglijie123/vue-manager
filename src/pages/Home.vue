<template>
  <div class="home">
    <Row class="header" type="flex" align="middle">
      <div class="logo">
        <img src="../assets/img/sf-logo.png" height="40" alt="">
        <span>顺丰科技</span>USM管理系统 <Tag>v1.0.0</Tag>
      </div>
      <VmMsgPush style=" position: absolute;right: 140px;" :data="msgPushData"></VmMsgPush>
      <Dropdown class="login-info" placement="bottom-end">
        <Button type="ghost" style="border: 0">
          <Avatar icon="person" src="https://i.loli.net/2017/08/21/599a521472424.jpg"/>
          管理员
            <Icon type="arrow-down-b"></Icon>
        </Button>
        <Dropdown-menu slot="list">
            <Dropdown-item divided><i class="fa fa-key"></i>Log out</Dropdown-item>
            <Dropdown-item divided><i class="fa fa-cog"></i>Setting</Dropdown-item>
        </Dropdown-menu>
      </Dropdown>
    </Row>
    <div class="sidebar">
      <Menu theme="dark" width="100%" class="menu" :active-name="activeName" :accordion="true">
          <Menu-item name="Dashboard">
              <router-link to="/">
                <i class="fa fa-dashboard"></i>
                用户管理
              </router-link>
          </Menu-item>
          <Menu-item name="Widget">
              <router-link to="/widget">
                <i class="fa fa-cogs"></i>
                渠道管理
              </router-link>
          </Menu-item>
          <Menu-item name="Panels">
              <router-link to="/panels">
                <i class="fa fa-database"></i>
                代理商信息
              </router-link>
          </Menu-item>
          <Menu-item name="Editor">
              <router-link to="/editor">
                <i class="fa fa-pencil"></i>
                文章发布
              </router-link>
          </Menu-item>
          <Menu-item name="ImageList">
              <router-link to="/imagelist">
                <i class="fa fa-photo"></i>
                图片资源
              </router-link>
          </Menu-item>
          <Menu-item name="Charts">
              <router-link to="/charts">
                <i class="fa fa-bar-chart"></i>
                报表管理
              </router-link>
          </Menu-item>
          <Submenu name="DataTable">
              <template slot="title">
                  <i class="fa fa-database"></i>
                  信息查询
              </template>
              <Menu-item name="BasicTable">
                <router-link to="/basic-table">
                  Basic Table
                </router-link>
              </Menu-item>
              <Menu-item name="EditableTable">
                <router-link to="/editable-table">
                  Editable Table
                </router-link>
              </Menu-item>
          </Submenu>
          <Submenu name="Pages">
              <template slot="title">
                  <i class="fa fa-file"></i>
                  Pages
              </template>
              <Menu-item name="Login">
                <router-link to="/login">
                  Login
                </router-link>
              </Menu-item>
              <Menu-item name="Lockscreen">
                <router-link to="/lockscreen">
                  Lockscreen
                </router-link>
              </Menu-item>
              <Menu-item name="Loading">
                <router-link to="/loading">
                  Loading
                </router-link>
              </Menu-item>
          </Submenu>
      </Menu>
    </div>
    <div class="main-content">
      <router-view></router-view>
      <p class="vm-author">vue-manager designed by <a href="https://github.com/luosijie" target="_blank">Jesse Luo</a></p>
    </div>
  </div>
  </div>
</template>
<script>
import VmMsgPush from '@/components/vm-msg-push.vue'
export default {
  name: 'home',
  components: {
    VmMsgPush
  },
  mounted: function () {
    this.activeName = this.$route.name
  },
  data () {
    return {
      activeName: 'Dashboard',
      msgPushData: [
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        }
      ]
    }
  }
}
</script>
