<template>
  <div>
    <MyHeader></MyHeader>
    <div class="article_list">
      <ul>
        <li v-for="i in list">
	  <time v-text="$utils.goodTime(i.create_at)"></time>
          <router-link :to="'/content/' + i.id">
            {{ i.title }}
          </router-link>
        </li>
      </ul>
    </div>
    <MyFooter></MyFooter>
  </div>
</template>
<script>
import MyHeader from '../components/header.vue'
import MyFooter from '../components/footer.vue'
export default {
  components: { MyHeader, MyFooter },
  data () {
    return {
      list: []
    }
  },
  created () {
    this.getData()
  },
  methods: {
    getData () {
      this.$api.get('topics', null, r => {
        this.list = r.data
        console.log(this.$route)
      })
    }
  }
}
</script>
<style>
  .article_list {margin: auto;}
</style>