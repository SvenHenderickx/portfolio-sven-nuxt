<script setup lang="ts">
defineProps<{
  post: {
    title: string
    subtitle: string
    tags: string
  }
}>()
</script>

<template>
  <div class="blog-card" :class="[`overviewsize-${post.overviewSize}`]">
    <div class="content">
      <h3 class="title">
        <NuxtLink class="covering-link" :to="post.path">
          {{ post.title }}
        </NuxtLink>
      </h3>
      <p>
        {{ post.subtitle }}
      </p>
      <ul class="tag-wrapper">
        <li class="tag" v-for="(tag, index) in post.tags" :key="index">
          {{ tag }}
        </li>
      </ul>
    </div>

    <NuxtImg class="image" :src="post.image" width="1200" height="1000" :alt="post.title">
    </NuxtImg>
  </div>
</template>

<style scoped>
.blog-card {
  padding: 24px;
  background: #303030;
  border: 1px solid #1d1d1d;
  min-height: 450px;
  transition: .2s ease-in;
  cursor: pointer;
  position: relative;
  border-radius: 16px;
  box-shadow: inset 0px 4px 14.100000381469727px 0px rgba(115, 115, 115, 25%), 0px 405px 113px 0px rgba(0, 0, 0, 0%), 0px 259px 104px 0px rgba(0, 0, 0, 1%), 0px 146px 87px 0px rgba(0, 0, 0, 5%), 0px 65px 65px 0px rgba(0, 0, 0, 9%), 0px 16px 36px 0px rgba(0, 0, 0, 10%);
  overflow: hidden;
}

.blog-card.overviewsize-1 {
  width: 100%;
}

.blog-card.overviewsize-2 {
  width: 50%;
}

.blog-card:hover {
  border: 1px solid #5b7281;
  box-shadow: inset 0px 4px 14.100000381469727px 0px rgba(115, 115, 115, 25%), 0px 405px 113px 0px rgba(0, 0, 0, 0%), 0px 259px 104px 0px rgba(0, 0, 0, 1%), 0px 146px 87px 0px rgba(88, 156, 168, 0.05), 0px 65px 65px 0px rgba(0, 0, 0, 9%), 0px 16px 36px 0px rgba(117, 167, 170, 0.1);
}

.image {
  z-index: 1;
  position: absolute;
  right: 0;
  object-fit: cover;

}

.blog-card.overviewsize-1 .image {
  top: 50%;
  transform: translateY(-50%);
  width: auto;
  height: 120%;
}

.blog-card.overviewsize-2 .image {
  height: 80%;
  bottom: 0;
}

.title {
  font-size: 24px;
  font-weight: 900;
  line-height: 1.1;
  margin-bottom: 8px;
}

.covering-link:after {
  content: '';
  position: absolute;
  display: block;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.content {
  z-index: 2;
  position: relative;
  width: 100%;
  height: 100%;
}

.tag-wrapper {
  display: flex;
}

.tag {
  margin-top: 32px;
  margin-right: 8px;
  background: black;
  padding: 4px 8px;
  font-size: 14px;
  color: white;
  text-transform: lowercase;
}
</style>
