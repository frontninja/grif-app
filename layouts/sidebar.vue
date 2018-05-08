<template>
  <div class="wrapper">
    <div class="content">
        <TheHeader/>
        <div class="container container_sidebar">
            <div class="sidebar">
                <side />
            </div>
            <div class="main">
                <nuxt/>
            </div>
        </div>
    </div>
    <TheFooter/>
  </div>
</template>
<script>
import TheHeader from '@/components/TheHeader/TheHeader.vue';
import TheFooter from '@/components/TheFooter/TheFooter.vue';
import side from '@/components/side.vue';

export default {
   components: {
    TheHeader,
    TheFooter,
    side
  }
}
</script>

<style lang="scss" scoped>
    .container_sidebar{
        display: flex;
    }
    .sidebar{
        width: 30%;
    }
    .main{
        width: 70%;
    }
</style>
