<template>
  <view>
    <uni-swiper-dot :info="info" :current="current" field="content" :mode="mode">
      <swiper class="swiper-box" @change="change">
        <swiper-item v-for="(item ,index) in info" :key="index">
          <view class="swiper-item">
            <div class="swiper-item-img" :style="{backgroundImage: 'url(' + item.path + ')' }"></div>
          </view>
        </swiper-item>
      </swiper>
    </uni-swiper-dot>
    <text class="router-info">{{text}}</text>
	<uni-list>
		<uni-list-item v-for="(item ,index) in travalInfo" :key="index" :title="item.title" :note="item.note" show-arrow="false" :thumb="item.thumb"></uni-list-item>
		<!-- <uni-list-item title="标题文字" note="描述信息" show-badge="true" badge-text="12"></uni-list-item> -->
	</uni-list>
  </view>
</template>

<script>
import { uniSwiperDot,uniListItem,uniList} from "@dcloudio/uni-ui";
export default {
  data() {
    return {
      text: "线路资讯",
      info: [
        {
          path: "../../static/swapper/swapper1.png"
        },
        {
          path: "../../static/swapper/swapper2.png"
        }
	  ],
	  travalInfo:[
		  {
			  title:'港澳游',
			  note:'精品港澳七天六夜游',
			  thumb:'http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png'
		  },
		  {
			  title:'港澳游',
			  note:'精品港澳七天六夜游',
			  thumb:'http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png'
		  },
		  {
			  title:'港澳游',
			  note:'精品港澳七天六夜游',
			  thumb:'http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png'
		  },{
			  title:'港澳游',
			  note:'精品港澳七天六夜游',
			  thumb:'http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png'
		  }
	  ],
      current: 0,
      mode: "default"
    };
  },
  methods: {
    change(e) {
      this.current = e.detail.current;
    }
  },
  components: {
	uniSwiperDot,
	uniList,
	uniListItem
  }
};
</script>

<style lang="css">
.swiper-item-img {
  width: 100%;
  height: 200px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.router-info {
  font-size: 12px;
  padding: 10px;
  display: block;
  text-align: center;
  color: #7a7e83;
}
</style>
