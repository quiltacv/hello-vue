<template>
    <div class="user-dashboard">
        <div class="list-user-comp">
          <h4>List User</h4>
          <ListUser @selectUser="listenSelectUser"></ListUser>
        </div>
        <div class="user-detail-comp">
          <h4> User Detail</h4>
          <UserDetail :userDetailInfo="userSelectFormDetail"></UserDetail>
        </div>
    </div>
</template>

<script>
    import ListUser from './ListUser.vue'
    import UserDetail from './UserDetail.vue'
    export default {
      components: {
        ListUser,
        UserDetail
      },
      data() {
        return {
          userSelectFormDetail: {}
        }
      },
      methods: {
        listenSelectUser(user) {
          this.userSelectFormDetail = user
        }
      }
    }
</script>

<style lang="scss" scoped>
</style>
