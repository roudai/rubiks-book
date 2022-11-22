<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-icon aria-label="目次" @click.stop="drawer = !drawer">{{
        icon.mdiForwardburger
      }}</v-icon>
      <v-toolbar-title>{{ title }}</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span
        >&copy; {{ new Date().getFullYear() }}
        <a href="https://roudai.net">roudai.net</a>
      </span>
    </v-footer>
  </v-app>
</template>

<script>
import { mdiForwardburger } from '@mdi/js'

export default {
  name: 'DefaultLayout',
  data() {
    return {
      icon: { mdiForwardburger },
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          title: '0. はじめに',
          to: '#chapter0',
        },
        {
          title: '1. 筆者について',
          to: '#chapter1',
        },
        {
          title: '2. ルービックキューブの大会とは',
          to: '#chapter2',
        },
        {
          title: '2-1. 誰が開催しているのか',
          to: '#chapter2-1',
        },
        {
          title: '2-2. 大会に出るには',
          to: '#chapter2-2',
        },
        {
          title: '2-3. 開催競技',
          to: '#chapter2-3',
        },
        {
          title: '2-4. 競技形式',
          to: '#chapter2-4',
        },
        {
          title: '2-5. 大会についてのQ&A',
          to: '#chapter2-5',
        },
        {
          title: '小話1 ルービックキューブはどれだけ難しいのか',
          to: '#short1',
        },
        {
          title: '3. 各競技の紹介',
          to: '#chapter3',
        },
        {
          title: '3-1. 3x3x3 キューブ',
          to: '#chapter3-1',
        },
        {
          title: '3-2. 2x2x2キューブ',
          to: '#chapter3-2',
        },
        {
          title: '3-3. 4x4x4キューブ',
          to: '#chapter3-3',
        },
        {
          title: '3-4. 5x5x5キューブ',
          to: '#chapter3-4',
        },
        {
          title: '3-5. 6x6x6キューブ',
          to: '#chapter3-5',
        },
        {
          title: '3-6. 7x7x7キューブ',
          to: '#chapter3-6',
        },
        {
          title: '小話2 スクランブルプログラムについて',
          to: '#short2',
        },
        {
          title: '3-7. 3x3x3 目隠し',
          to: '#chapter3-7',
        },
        {
          title: '3-8. 3x3x3 最少手数',
          to: '#chapter3-8',
        },
        {
          title: '3-9. 3x3x3 片手',
          to: '#chapter3-9',
        },
        {
          title: '3-10. 3x3x3 足',
          to: '#chapter3-10',
        },
        {
          title: '小話3 大会での不正について',
          to: '#short3',
        },
        {
          title: '3-11. ルービッククロック',
          to: '#chapter3-11',
        },
        {
          title: '3-12. メガミンクス',
          to: '#chapter3-12',
        },
        {
          title: '3-13. ピラミンクス',
          to: '#chapter3-13',
        },
        {
          title: '3-14. スキューブ',
          to: '#chapter3-14',
        },
        {
          title: '3-15. スクエア1',
          to: '#chapter3-15',
        },
        {
          title: '小話4 視覚障がい者とルービックキューブ',
          to: '#short4',
        },
        {
          title: '3-16. 4x4x4 目隠し',
          to: '#chapter3-16',
        },
        {
          title: '3-17. 5x5x5 目隠し',
          to: '#chapter3-17',
        },
        {
          title: '3-18. 3x3x3 複数目隠し',
          to: '#chapter3-18',
        },
        {
          title: 'まとめ',
          to: '#summary',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '目次',
    }
  },
}
</script>

<style>
.v-icon {
  margin-right: 0.5rem;
}
.v-application a {
  color: #ffffff !important;
  text-decoration: none;
}
</style>
