<template>
  <div id="sendOutManage">
    <component :is="current"></component>
  </div>
</template>
<script>
  import sendOutList from '@/components/reprintManage/sendOutManage/sendOutList.vue'

  export default {
    name: 'sendOutManage',
    data() {
      return {
        current: 'sendOutList',
      }
    },
    watch: {
      '$route': function (newValue, oldValue) {
        if (newValue.query.name !== oldValue.query.name) {
          this.listenRouter();
        }
      }
    },
    mounted: function () {
    },
    methods: {
      //监听路由发生变化
      listenRouter() {
        if (this.$route.query.name) {
          this.current = this.$route.query.name;
        }
      },
    },
    components: {
      sendOutList,
    }
  }
</script>
