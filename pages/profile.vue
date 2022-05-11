<template>
  <v-row>
    <v-col>
      <v-img
        contain
        max-height="540"
        max-width="810"
        src="/image/profile.jpg"
      ></v-img>
      <!-- <blockquote class="blockquote">
          1994年 生まれ
          2017年 東京都立大学インダストリアルアートコース 卒業
          2022年 情報科学芸術大学院大学 卒業



        &#8220;First, solve the problem. Then, write the code.&#8221;
      </blockquote> -->
      <v-card>
        <v-card-title class="headline"> Ayumi Nagai </v-card-title>
        <v-card-text>
          <p>最近の専門は幻覚剤とVR。</p>
          <p>
            2022年 情報科学芸術大学院大学(IAMAS) メディア表現研究科
            博士前期課程修了<br />
            2017年
            首都大学東京(現東京都立大学)システムデザイン学部インダストリアルアートコース
            卒業
          </p>
          <p>2018年～2020年 総合映像制作会社 技術職</p>

          <v-btn
            class="ma-2"
            text
            icon
            href="https://twitter.com/stu_0120"
            target="_blank"
          >
            <v-icon>mdi-twitter</v-icon>
          </v-btn>
          <v-btn
            class="ma-2"
            text
            icon
            href="mailto:aym-ngi20@iamas.ac.jp"
            target="_blank"
          >
          <v-icon> mdi-email </v-icon>
          </v-btn>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  build: {
    loaders: {
      vue: {
        prettify: false,
      },
    },
  },
  name: 'ProfilePage',
}
</script>