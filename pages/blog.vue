<script setup>
import { useWindowSize } from '@vueuse/core';
const { width, height } = useWindowSize();

/* placeholder data */
const posts = [
  {
    id: '1',
    data: {
      image: '/blog/feature-matrix@2x.jpg',
      icon: '/blog/icon-matrix@2x.jpg',
      date: 'March 01, 2024',
      title: 'Matrix Phone Booth: Immersive Experiences in Openhome',
      excerpt:
        'We are thrilled to spotlight this creative community project from OpenHome community member Tracy Tao!',
      url: 'https://openhome.xyz/matrix-phone-booth-what-would-you-choose/',
    },
  },
  {
    id: '1',
    data: {
      image: '/news-thumb1@2x.jpg',
      icon: '/news-icon1@2x.png',
      date: 'April 02, 2024',
      title: 'Introducing MetaCap: Live Emotional Insights Come to OpenHome',
      excerpt:
        "We're thrilled to showcase a community project built by members of the OpenHome developer community! At the heart of OpenHome's",
      url: 'https://openhome.xyz/introducing-metacap-live-emotional-insights-are-coming-to-openhome/',
    },
  },
  {
    id: '2',
    data: {
      image: '/news-thumb2@2x.jpg',
      icon: '/news-icon2@2x.png',
      date: 'March 01, 2024',
      title: 'Matrix Phone Booth: Immersive Experiences in Openhome',
      excerpt:
        'We are thrilled to spotlight this creative community project from OpenHome community member Tracy Tao!',
      url: 'https://openhome.xyz/matrix-phone-booth-what-would-you-choose/',
    },
  },
  ,
  {
    id: '2',
    data: {
      image: '/news-thumb2@2x.jpg',
      icon: '/news-icon2@2x.png',
      date: 'March 01, 2024',
      title: 'Matrix Phone Booth: Immersive Experiences in Openhome',
      excerpt:
        'We are thrilled to spotlight this creative community project from OpenHome community member Tracy Tao!',
      url: 'https://openhome.xyz/matrix-phone-booth-what-would-you-choose/',
    },
  },
  {
    id: '2',
    data: {
      image: '/news-thumb2@2x.jpg',
      icon: '/news-icon2@2x.png',
      date: 'March 01, 2024',
      title: 'Matrix Phone Booth: Immersive Experiences in Openhome',
      excerpt:
        'We are thrilled to spotlight this creative community project from OpenHome community member Tracy Tao!',
      url: 'https://openhome.xyz/matrix-phone-booth-what-would-you-choose/',
    },
  },
  {
    id: '2',
    data: {
      image: '/news-thumb2@2x.jpg',
      icon: '/news-icon2@2x.png',
      date: 'March 01, 2024',
      title: 'Matrix Phone Booth: Immersive Experiences in Openhome',
      excerpt:
        'We are thrilled to spotlight this creative community project from OpenHome community member Tracy Tao!',
      url: 'https://openhome.xyz/matrix-phone-booth-what-would-you-choose/',
    },
  },
  {
    id: '1',
    data: {
      image: '/news-thumb1@2x.jpg',
      icon: '/news-icon1@2x.png',
      date: 'April 02, 2024',
      title: 'Introducing MetaCap: Live Emotional Insights Come to OpenHome',
      excerpt:
        "We're thrilled to showcase a community project built by members of the OpenHome developer community! At the heart of OpenHome's",
      url: 'https://openhome.xyz/introducing-metacap-live-emotional-insights-are-coming-to-openhome/',
    },
  },
  {
    id: '1',
    data: {
      image: '/news-thumb1@2x.jpg',
      icon: '/news-icon1@2x.png',
      date: 'April 02, 2024',
      title: 'Introducing MetaCap: Live Emotional Insights Come to OpenHome',
      excerpt:
        "We're thrilled to showcase a community project built by members of the OpenHome developer community! At the heart of OpenHome's",
      url: 'https://openhome.xyz/introducing-metacap-live-emotional-insights-are-coming-to-openhome/',
    },
  },
];

let show_posts = posts.filter((post, i) => i > 0);
</script>

<template>
  <div class="main-contents">
    <div class="resources section-wrapper lt">
      <!-- header -->
      <div class="row gridlines hero np-bot">
        <Gridlines />
        <div class="side-ornament lt"><div class="circ"></div></div>
        <div class="side-ornament rt">
          <img src="/public/icons/logo-halfcircs.svg" alt="" />
        </div>

        <div class="content-wrapper header p-max">
          <header>
            <Headline>
              <h2 class="alt">
                Res<span class="pix">o</span>u<span class="pix">r</span>c<span
                  class="pix"
                  >e</span
                >s
              </h2>
            </Headline>
          </header>
        </div>
      </div>

      <!-- featured post -->
      <div class="row gridlines np-bot">
        <Gridlines />
        <div class="content-wrapper no-max">
          <div class="feature col pad">
            <BlogFeature :data="posts[0].data" />
            <BlogFilter />
          </div>
        </div>
      </div>

      <!-- grid -->
      <div
        class="blog-grid row gridlines np-bot"
        :class="width <= 900 && 'stack'"
      >
        <Gridlines bot="true" pad="nopad" />
        <div class="content-wrapper no-max">
          <div class="grid three-col">
            <BlogThumb
              v-for="(post, key) in show_posts"
              :data="post.data"
              :id="key"
            />
            <div class="blog-grid-spacer"></div>
            <div class="blog-grid-spacer"></div>
          </div>
        </div>
      </div>

      <!-- pagination -->
      <div class="pagination row gridlines np-bot">
        <Gridlines />
        <div class="content-wrapper no-max">1 2 3 4</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.resources {
  header {
    padding-top: 3.2rem;
    padding-bottom: 3.2rem;
  }
}
.feature {
  padding-top: 25px;
  padding-bottom: 32px;
  .tags {
    margin-top: 30px;
  }
}
.pagination {
  text-align: center;
}
</style>
