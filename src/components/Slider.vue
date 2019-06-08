<template>
  <div id="banner" :style="{'background-image':bgImg}">
    <div id="context-list">
      <img id="icon" :src="imgArray[indexNum].icon">
      <label id="content">{{imgArray[indexNum].content}}</label>
      <button id="title">{{imgArray[indexNum].title}}</button>
    </div>
    <button id="btn-left" @click="indexNum--">&lt;</button>
    <button id="btn-right" @click="indexNum++">&gt;</button>
  </div>
</template>

<script>
export default {
  name: "test",
  data: () => {
    let imgArray = [
      {
        icon: "/image/icon1.png",
        url: "/image/img1.jpg",
        title: "img1",
        content: "First item"
      },
      {
        icon: "/image/icon2.png",
        url: "/image/img2.jpg",
        title: "img2",
        content: "Second item"
      },
      {
        icon: "/image/icon3.png",
        url: "/image/img3.jpg",
        title: "img3",
        content: "Third item"
      }
    ];
    return {
      indexNum: 0,
      imgArray: imgArray
    };
  },
  computed: {
    bgImg() {
      return `url(${this.imgArray[this.indexNum].url})`;
    }
  }
};
</script>

<style>
#banner {
  position: relative;
  background-color: gray;
  background-size: cover;
  padding-top: 50%;
}
#context-list {
  position: absolute;
  top: 20%;
  left: 15%;
  display: flex;
  flex-direction: column;
}
#icon {
  max-height: 100px;
}
#content {
  font-size: 30px;
  margin-top: 30px;
}
#title {
  font-size: 30px;
  margin-top: 30px;
}

#btn-left {
  position: absolute;
  top: 50%;
  left: 0;
}
#btn-right {
  position: absolute;
  top: 50%;
  right: 0;
}
</style>
