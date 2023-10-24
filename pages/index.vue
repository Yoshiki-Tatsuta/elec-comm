<template lang="pug">
-
  var images_alt = "画像が挿入されていません。";

v-app
  v-low.text-center
    h1.blue--text.text--lighten-2 夢の国へ、ようこそ！
  br
  v-carousel(hide-delimiters, cycle, :interval="10000", height="500px", progress=true, progress-color="white" show-arrows-on-hover=true)
    v-carousel-item(v-for="(item, i) in items" :key="i")
      v-img(:src="item.src", contain :style="{ 'max-height': '500px', 'width': 'auto' }")
  br
  v-low.text-center 
    h2.yellow--text.text--lighten-2 ピックアップ商品
  br
  v-container
    .pickup-ul
      v-layout(row wrap)
        v-flex(xs4 v-for="(pick1, i) in picks1" :key="i").text-center
          a(:href="pick1.href")
            img(:src="pick1.src", alt=images_alt)
          a(:href="pick1.href")
            p {{ pick1.p }}
          ul
            li {{ pick1.li1 }}
            li {{ pick1.li2 }}
        v-flex(xs4 v-for="(pick2, i) in picks2" :key="i").text-center
          a(:href="pick2.href")
            img(:src="pick2.src", alt=images_alt)
          a(:href="pick2.href")
            p {{ pick2.p }}
          ul
            li {{ pick2.li1 }}
            li {{ pick2.li2 }}
        v-flex(xs4 v-for="(pick3, i) in picks3" :key="i").text-center
          a(:href="pick3.href")
            img(:src="pick3.src", alt=images_alt)
          a(:href="pick3.href")  
            p {{ pick3.p }}
          ul
            li {{ pick3.li1 }}
            li {{ pick3.li2 }}
  br
  br
  .favorite-items
    v-low.text-center
      h2.yellow--text.text--lighten-2 おすすめの商品
    v-carousel(height="400px", cycle, :interval="15000")
      v-carousel-item
        v-container
          v-layout(row)
            v-flex(xs4 v-for="(icon, j) in icons1" :key="j").text-center
              a(:href="icon.href")
                img(:src="icon.src")
                p {{ icon.p1 }}
              p {{ icon.p2 }}
      v-carousel-item
        v-container
          v-layout(row)
            v-flex(xs4 v-for="(icon, j) in icons2" :key="j").text-center
              a(:href="icon.href")
                img(:src="icon.src")
                p {{ icon.p1 }}
              p {{ icon.p2 }}
</template>


<script lang="ts">
export default  {
  name: 'IndexPage',
  data() {
    return {
      items: [
        { src: 'images/dis_chs4.jpeg' },
        { src: 'images/dis_chs5.jpeg' },
        { src: 'images/dis_chs3.jpeg' },
        { src: 'images/dis_chs6.jpg' }
      ],
      icons1: [
        { src: 'icons/icon1.png', p1: 'アイコン1', p2: '300円', href: '#' },
        { src: 'icons/icon2.jpg', p1: 'アイコン2', p2: '300円', href: '#' },
        { src: 'icons/icon3.jpg', p1: 'アイコン3', p2: '300円', href: '#' }
      ],
      icons2: [
        { src: 'icons/icon1.png', p1: 'アイコン4', p2: '300円', href: '#' },
        { src: 'icons/icon2.jpg', p1: 'アイコン5', p2: '300円', href: '#' },
        { src: 'icons/icon3.jpg', p1: 'アイコン6', p2: '300円', href: '#' }
      ],
      picks1: [
        { 
          p: 'お城',
          href: '#',
          src: '/images/dis_chs.jpg',
          li1: '3,000円',
          li2: 'new'
        }
      ],
      picks2: [
        { 
          p: 'アイコン',
          href: '#',
          src: 'favicon.ico',
          li1: '2,500円',
          li2: 'new'
        }
      ],
      picks3: [
        { 
          p: '写真',
          href: '#',
          src: '/images/dis_chs2.jpg',
          li1: '6,200円',
          li2: ''
        }
      ]
    }
  }
}
</script>

<style scoped>
.pickup-ul ul {
  list-style-type: none;
  padding-left: 0;
}
.pickup-ul img {
  width: 300px;
  height: 200px;
  padding-bottom: 10px;
}
.favorite-items h2 {
  padding-bottom: 30px;
}
</style>