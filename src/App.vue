<template lang='pug'>
#app
  el-menu(
    :default-active="activeIndex",
    menu-trigger="hover",
    mode="horizontal",
    @select="handleSelect",
    text-color="#000",
    background-color="#FAEBEB",
    letter-spacing="0.4em"
  )
    el-menu-item.E
    el-menu-item.L 
    el-menu-item.A IPTA 藝術學院學士班
    el-menu-item.nthuipta(index="1", menu-trigger="hover") 國立清華大學藝術學院
    el-menu-item.nthuipta(index="2", menu-trigger="hover") 首頁
    el-menu-item.nthuipta(index="3", menu-trigger="hover") 最新消息
    el-submenu.nthuipta(index="4", menu-trigger="hover") 
      template.nthuipta(slot="title") 招生資訊
      el-menu-item.nthuipta(index="4-1") 春之清華卓越獎五名
      el-menu-item.nthuipta(index="4-2") 學士班臉書粉絲頁
      el-submenu.nthuipta(index="4-3", menu-trigger="hover") 
        template.nthuipta(slot="title") ２０２０招生資訊
        el-menu-item(index="4-3-1") ２０２０錄取名單
        el-menu-item(index="4-3-2") ２０２０招生簡章
        el-menu-item(index="4-3-3") ２０２０個人申請第二階段甄選注意事項
        el-menu-item(index="4-3-3") ２０２０報名繳交資料
      el-menu-item.nthuipta(index="4-4") 招生Ｑ＆Ａ
      el-submenu.nthuipta(index="4-5", menu-trigger="hover") 
        template(slot="title") 過往招生資訊
        el-submenu.nthuipta(index="4-5-1", menu-trigger="hover") 
          template.nthuipta(slot="title") ２０１９年招生資訊
          el-menu-item(index="4-5-1-1") ２０１９錄取名單
          el-menu-item(index="4-5-1-2") ２０１９招生簡章
          el-menu-item(index="4-5-1-3") ２０１９個人申請第二階段甄選注意事項
          el-menu-item(index="4-5-1-4") ２０１９報名繳交資料
        el-submenu.nthuipta(index="4-5-2", menu-trigger="hover") 
          template.nthuipta(slot="title") ２０１８年招生資訊
          el-menu-item(index="4-5-2-1") ２０１８錄取名單
          el-menu-item(index="4-5-2-2") ２０１８招生簡章
          el-menu-item(index="4-5-2-3") ２０１８個人申請第二階段甄選注意事項
          el-menu-item(index="4-5-2-4") ２０１８報名繳交資料
    el-submenu.nthuipta(index="5", menu-trigger="hover") 
      template.nthuipta(slot="title") 學士班
      el-menu-item.nthuipta(index="5-1") 學士班簡介
      el-menu-item.nthuipta(index="5-2") 學士班課程
      el-menu-item.nthuipta(index="5-3") 國際交換
      el-menu-item.nthuipta(index="5-4") 藝術學院大樓(New)
    el-submenu.nthuipta(index="6", menu-trigger="hover") 
      template.nthuipta(slot="title") 師資
      el-menu-item.nthuipta(index="6-1") 學士班師資
      el-menu-item.nthuipta(index="6-2") 藝設系師資
      el-menu-item.nthuipta(index="6-3") 音樂系師資
      el-menu-item.nthuipta(index="6-4") 電資學院師資
    el-submenu.nthuipta(index="7", menu-trigger="hover") 
      template.nthuipta(slot="title") 科藝賞析
      el-menu-item.nthuipta(index="7-1") 數位文創作品
      el-menu-item.nthuipta(index="7-2") 互動藝術作品
      el-menu-item.nthuipta(index="7-3") 動力藝術作品
      el-menu-item.nthuipta(index="7-4") 聲音藝術作品
      el-menu-item.nthuipta(index="7-4") 科技表演藝術
    el-menu-item.nthuipta(index="8", menu-trigger="hover") 聯絡我們
  .bllia
  .header
    .rect
    .circle.circle1 核心能力
    .circle.circle2 學士班特色
    .header_word
      .header_word1 國立清華大學
      .header_word2 藝術學院學士班

  .bllii
  .news
    .news_rect_word 最新消息
    .news_flex
      .news_item(v-for="item in newsList")
        .news_img(:style="{ backgroundImage: 'url(' + item.img + ')' }")
        .news_text {{ item.text }}
  .works
    .works_rect_word 優秀作品
    .works_flex
      .works_item(v-for="item in worksList")
        .works_img(:style="{ backgroundImage: 'url(' + item.img + ')' }")
        .works_text {{ item.text }}
  .blli
  .scho
    .scho_rect_word 最酷的系，要的是最酷的你！
    .scho_rect
      .scho_blli
      .scho_img
        .scho_text 春之清華獎學金
  .tail
    .tail_rect
    .tail_flex
      .tail_item(v-for="item in List")
        .tail_text {{ item.text }}
  router-view
</template>

<script>
// // @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      newsList: [
        {
          img: "http://ipta.nthu.edu.tw/wp-content/uploads/2020/05/200528.jpg",
          text:
            "【獲獎】《那顆Ｇ1咻！》國立清華大學藝術學院學士班第一屆系展 得獎名單",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "【獲獎】2020春之清華 – 藝術卓越獎 科技藝術類 得獎名單",
        },
        {
          img: "http://ipta.nthu.edu.tw/wp-content/uploads/2020/05/200528.jpg",
          text: "《那顆Ｇ1咻！》國立清華大學藝術學院學士班第一屆系展",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01.jpg",
          text: "【獲獎】2020藝術學院學士班春之清華獎學金 獲獎名單",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "徵件公告】春之清華—藝術卓越獎科技藝術類 甄選辦法",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學 藝術學院學士班 徵聘【助理教授級以上】專任教師1名",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01.jpg",
          text: "《 科技物件與人類幻象講座 Ⅸ》6/16 Tue",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text:
            "【演講】05/28 從腦科學看藝術 (Art and the Brain: A Glimpse of Neuroaesthetics)",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
      ],
      worksList: [
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text:
            "【演講】05/28 從腦科學看藝術 (Art and the Brain: A Glimpse of Neuroaesthetics)",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
        {
          img:
            "https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01-768x340.jpg",
          text: "國立清華大學藝術學院學士班公開徵求班主任候選人啟事",
        },
      ],
      List: [
        { text: " IPTA 藝術學院學士班" },
        { text: "國立清華大學藝術學院" },
        { text: "HOME" },
        { text: "最新消息" },
        { text: "招生資訊" },
        { text: "學士班" },
        { text: "師資" },
        { text: "科藝欣賞" },
        { text: "聯絡我們" },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.bllia {
  width: 100%;
  height: 5px;
  background-color: black;
}
.header {
  position: relative;
  width: 100%;
  height: 903px;
  background-image: url("./assets/thisisengineering.jpg");
  background-size: cover;
  overflow: hidden;
}
.rect {
  width: 100%;
  height: 100%;
  background-color: #fff;
  opacity: 60%;
}
.circle {
  position: absolute;
  background-color: #faebeb;
  border-radius: 50%;
  font-size: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12), 0 0 6px rgba(0, 0, 0, 0.04);
}
.circle1 {
  top: 64px;
  right: -67px;
  padding: 120px 140px 120px 100px;
}
.circle2 {
  bottom: 150px;
  left: -107px;
  padding: 120px 100px 120px 140px;
}
.header_word {
  width: 485px;
  font-size: 69px;
  text-align: center;
  position: absolute;
  top: 450px;
  right: 470px;
}
.bllii {
  width: 100%;
  height: 5px;
  background-color: black;
}
.news {
  display: flex;
  flex-direction: column;
  background-color: #faebeb;
}
.news_rect {
  width: 100%;
  height: 900px;
  background-color: #faebeb;
}
.news_rect_word {
  font-weight: bold;
  /* position: absolute; */
  padding: 20px 20px 0px 20px;
  right: 540px;
  font-size: xx-large;
}
.news_flex {
  width: 80%;
  margin: auto;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
.news_item {
  width: 300px;
  padding: 20px;
}
.news_img {
  width: 296px;
  height: 167px;
  background-size: cover;
  border-radius: 10%;
}
.news_item {
  padding: 5px;
}
.scho_blli {
  width: 100%;
  height: 5px;
  background-color: black;
}
.works {
  display: flex;
  flex-direction: column;
  background-color: #95dae5;
}
.works_rect {
  width: 100%;
  height: 1200px;
  background-color: #95dae5;
  opacity: 30%;
}
.works_item {
  padding: 20px;
}
.works_flex {
  width: 80%;
  margin: auto;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0px 20px 20px 20px;
}
.works_rect_word {
  font-weight: bold;
  /* position: absolute; */
  padding: 20px;
  right: 540px;
  font-size: xx-large;
}
.works_img {
  width: 296px;
  height: 167px;
  background-size: cover;
  border-radius: 10%;
}
.works_text {
  width: 296px;
}
.news_item {
  width: 300px;
  padding: 20px;
}
.news_rect {
  width: 100%;
  height: 1000px;
  background-color: #faebeb;
}
.blli {
  width: 100%;
  height: 5px;
  background-color: black;
}
.scho {
  display: flex;
  flex-direction: column;
  background-color: #faebeb;
}
.scho_rect {
  width: 100%;
  height: 760px;
  background-color: #95dae5;
}
.scho_rect_word {
  font-weight: bold;
  /* position: absolute; */
  padding: 20px;
  right: 540px;
  font-size: xx-large;
}
.scho_img {
  /* position: relative; */
  margin-top: 50px;
  width: 100%;
  height: 660px;
  background-image: url("https://upload.cc/i1/2020/12/22/vkwYZL.jpg");
  background-size: cover;
  opacity: 74%;
}
.scho_text {
  width: 100%;
  z-index: 9999;
  padding-top: 300px;
  font-size: 45px;
  color: black;
  font-weight: bolder;
}
.tail_flex {
  width: 100%;
  height: 70px;
  background-color: #faebeb;
  width: 100%;

  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
.tail_rect {
  width: 100%;
  height: 5px;
  background-color: black;
}
.tail_text {
  font-size: 25px;
  padding: 10px;
}
</style>