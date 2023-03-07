<script setup>
import { onMounted, ref } from 'vue'

import UserImage from '../components/UserImage.vue'
import ProfileHeader from '../components/ProfileHeader.vue'
import UserInfo from '../components/UserInfo.vue'
import AccountInfo from '../components/AccountInfo.vue'

const profile = ref('')

onMounted(async () => {
  const res = await fetch('https://api.github.com/users/alvinokafor')
  const result = await res.json()
  profile.value = result
  // console.log(profile.value)
})

// console.log(profile.value)
</script>

<template>
  <main>
    <section class="homeContainer flex">
      <div>
        <UserImage :img="profile.avatar_url" />
      </div>

      <div class="content">
        <ProfileHeader :bio="profile.bio" :name="profile.name" :username="profile.login" />
        <AccountInfo
          :followers="profile.followers"
          :following="profile.following"
          :repos="profile.public_repos"
        />
        <UserInfo
          :location="profile.location"
          :url="profile.html_url"
          :twitter="profile.twitter_username"
        />
      </div>
    </section>
  </main>
</template>

<style scoped>
.homeContainer {
  background-color: var(--secondary);
  max-width: 1024px;
  margin-inline: auto;
  margin-block: 20px;
  padding-inline: 40px;
  padding-block: 60px;
  border-radius: 8px;
}

.content {
  width: 100%;
}

@media (max-width: 420px) {
  .homeContainer {
    max-width: 90%;
    flex-direction: column;
    padding-inline: 20px;
  }
}
</style>
