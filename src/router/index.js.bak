import Vue from 'vue'
import Router from 'vue-router'
import Index from '@/page/index'
import Content from '@/page/content'
// 引入子路由
import Frame from '@/frame/subroute.vue'
// 引入子页面
import userIndex from '@/page/user/index.vue'
import userInfo from '@/page/user/info.vue'
import userLove from '@/page/user/love.vue'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'Index',
      component: Index
    },
    {
      path: '/content/:id',
      name: 'Content',
      component: Content
    },
    {
      path: '/user',
      component: Frame,
      children: [
        {path: '/', component: userIndex},
        {path: 'info', component: userInfo},
        {path: 'love', component: userLove}
      ]
    }
  ]
})
