<!-- 使用 type="home" 属性设置首页，其他页面不需要设置，默认为page；推荐使用json5，更强大，且允许注释 -->
<route lang="json5" type="home">
{
  style: {
    navigationStyle: 'custom',
    navigationBarTitleText: '首页',
  },
}
</route>
<template>
  <view class="bg-[#f9fafb] overflow-hidden" :style="{ marginTop: safeAreaInsets?.top + 'px' }">
    <view style="min-height: 200px; background-color: #f9fafb">
      <img
        src="/static/images/index1.png"
        alt="Image not found"
        style="display: block; width: 100%; height: auto; object-fit: contain"
      />
    </view>

    <view class="flex items-center pt-8">
      <view class="mr-4">
        <view class="mb-4" style="width: 80rpx; height: 4rpx; background-color: #ed6301"></view>
      </view>
      <view class="text-left">
        <h1
          class="mb-2"
          style="font-size: 28rpx; font-weight: 500; line-height: 28rpx; color: #d0d0d0"
        >
          ABOUT US
        </h1>
        <h2
          class="mb-6"
          style="font-size: 28rpx; font-weight: 500; line-height: 28rpx; color: #262626"
        >
          关于冀弘
        </h2>
      </view>
    </view>

    <view style="color: #858585" class="text-justify max-w-100 m-auto text-3 indent mb-2 px-6">
      {{ description1 }}
    </view>
    <view style="color: #858585" class="text-justify max-w-100 m-auto text-3 indent mb-2 px-6">
      {{ description2 }}
    </view>

    <view class="mt-6">
      <img
        src="/static/images/index2.png"
        alt="Image not found"
        style="display: block; width: 100%; height: auto; object-fit: contain"
      />
    </view>

    <view
      class="mt-6 h-[150rpx] flex flex-row justify-center items-center mx-6 bg-white rounded-sm shadow-sm"
    >
      <view class="flex-1 flex flex-col items-center justify-center">
        <wd-count-to :fontSize="22" :endVal="99" suffix="人" color="#ED6301"></wd-count-to>
        <view class="text-center text-xs text-gray-500">技术人员</view>
      </view>
      <div class="h-8 w-px bg-gray-200"></div>
      <view class="flex-1 flex flex-col items-center justify-center">
        <wd-count-to
          prefix=""
          :startVal="0"
          :decimals="0"
          :endVal="10"
          :fontSize="22"
          suffix="年"
          color="#ED6301"
        ></wd-count-to>
        <view class="text-center text-xs text-gray-500">公司历程</view>
      </view>
      <div class="h-8 w-px bg-gray-200"></div>
      <view class="flex-1 flex flex-col items-center justify-center">
        <wd-count-to
          prefix=""
          :startVal="0"
          :decimals="0"
          :endVal="239"
          :fontSize="22"
          suffix="家"
          color="#ff5722"
        ></wd-count-to>
        <view class="text-center text-xs text-gray-500">合作客户</view>
      </view>
      <div class="h-8 w-px bg-gray-200"></div>
      <view class="flex-1 flex flex-col items-center justify-center">
        <wd-count-to
          prefix=""
          :startVal="0"
          :decimals="0"
          :endVal="35"
          :fontSize="22"
          suffix="个"
          color="#ED6301"
          :duration="2000"
        ></wd-count-to>
        <view class="text-center text-xs text-gray-500">取得荣誉</view>
      </view>
    </view>

    <view class="flex items-center pt-8">
      <view class="mr-4">
        <view class="mb-4" style="width: 80rpx; height: 4rpx; background-color: #ed6301"></view>
      </view>
      <view class="text-left">
        <h1
          class="mb-2"
          style="font-size: 28rpx; font-weight: 500; line-height: 28rpx; color: #d0d0d0"
        >
          ENGINEERING CASE
        </h1>
        <h2
          class="mb-6"
          style="font-size: 28rpx; font-weight: 500; line-height: 28rpx; color: #262626"
        >
          我们的资质
        </h2>
      </view>
    </view>

    <view class="card-swiper">
      <wd-swiper
        autoplay
        v-model:current="current"
        :display-multiple-items="2"
        custom-indicator-class="custom-indicator-class"
        custom-image-class="custom-image"
        custom-next-image-class="custom-image-prev"
        custom-prev-image-class="custom-image-prev"
        :indicator="{ type: 'dots' }"
        :list="swiperList"
        previousMargin="24px"
        nextMargin="24px"
        imageMode="aspectFit"
      ></wd-swiper>
    </view>
    <view
      class="flex flex-col mt-[60rpx]"
      style="
        height: 490rpx;
        background-image: url('/static/images/153@1x.png');
        background-position: center;
        background-size: 100% auto;
      "
    >
      <view>
        <view style="height: 140rpx" class="flex flex-row items-center justify-between">
          <view class="flex items-center pt-8">
            <view class="mr-4">
              <view
                class="mb-4"
                style="width: 80rpx; height: 4rpx; background-color: #ed6301"
              ></view>
            </view>
            <view class="text-left">
              <h1
                class="mb-2"
                style="font-size: 26rpx; font-weight: 500; line-height: 26rpx; color: #d0d0d0"
              >
                PRODUCT CENTER
              </h1>
              <h2
                class="mb-4"
                style="font-size: 26rpx; font-weight: 500; line-height: 26rpx; color: #d0d0d0"
              >
                产品中心
              </h2>
            </view>
          </view>
          <view class="flex flex-row items-center">
            <wd-button size="small" type="warning" @click="prevProduct">上一个</wd-button>
            <wd-button size="small" type="warning" @click="nextProduct" style="margin-left: 20rpx">
              下一个
            </wd-button>
          </view>
        </view>
      </view>
      <view class="w-full flex flex-row pt-[40rpx]" style="flex: 1">
        <view
          style="width: 42%; height: 100%; background-color: #fff"
          class="flex flex-col items-center justify-center"
        >
          <text class="text-sm font-bold" style="font-size: 24rpx; color: #262626">
            {{ products[currentIndex]?.title }}
          </text>
          <text class="pt-[10rpx] px-4 truncate-text" style="font-size: 16rpx; color: #8d8d8d">
            {{ products[currentIndex]?.description }}
          </text>
          <view class="pt-2"><wd-button type="warning" size="small">了解详情</wd-button></view>
        </view>

        <view style="width: 58%; height: 100%" v-if="products[currentIndex]?.ico">
          <img
            :src="`${VITE_SERVER_BASEURL}${products[currentIndex]?.ico}`"
            style="width: 100%; height: 100%; object-fit: cover"
          />
        </view>
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import { http, httpGet } from '@/utils/http'
defineOptions({
  name: 'Home',
})

// 获取屏幕边界到安全区域距离
const { safeAreaInsets } = uni.getSystemInfoSync()
const description1 = ref(
  '广东冀弘钢管有限公司位于广东省佛山市高明工业区。成立至今已初具规模，充足的货源，优质的服务，坚若怨石的质量，完蕃的售后服务,在业内有了一定声誉的“特级信用”企业。',
)
const description2 = ref(
  '公司主要经营产品有钢板类簟、螺旋钢篢、焊接钢篢、钢管防腐、熔结环领纷未防腐、钢护简等产品，产品广泛应用于市政工程、供水管道、污水排放、打桩、梁护简、石油天然与输送、热力发电、钢结构、机械制造、建筑工程、公用事业、造船工业、电站等多个方面领域。进行从原材料到产品的出场的100%的合格率，做到客户无忧使用。',
)

const current = ref<number>(0)
type IFooItem = { name: string }
const { loading, error, data, run } = useRequest<IFooItem>(() => httpGet('/api.php/list/4'))
const {
  loading: loading2,
  error: error2,
  data: data2,
  run: run2,
} = useRequest<IFooItem>(() => httpGet('/api.php/list/5'))

const swiperList = ref([
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/redpanda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/capybara.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/panda.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/moon.jpg',
  'https://registry.npmmirror.com/wot-design-uni-assets/*/files/meng.jpg',
])
const VITE_SERVER_BASEURL = 'http://8.138.129.19'
// 测试 uni API 自动引入
onLoad(async () => {
  const res = await run()
  // 提取 ico 字段到 swiperList
  swiperList.value = []
  swiperList.value = res.map((item) => `${VITE_SERVER_BASEURL}${item.ico}`)
  products.value = await run2()
  // console.log(products.value)
})

const products = ref([]) // 产品列表
const currentIndex = ref(0) // 当前产品索引
// 更新产品信息
function updateProduct() {
  if (products.value.length > 0) {
    const currentProduct = products.value[currentIndex.value]
    console.log(currentProduct.title) // 显示当前产品标题
  }
}

// 切换到下一个产品
function nextProduct() {
  if (currentIndex.value < products.value.length - 1) {
    currentIndex.value++
  } else {
    currentIndex.value = 0 // 循环到第一个产品
  }
  updateProduct()
}

// 切换到上一个产品
function prevProduct() {
  if (currentIndex.value > 0) {
    currentIndex.value--
  } else {
    currentIndex.value = products.value.length - 1 // 循环到最后一个产品
  }
  updateProduct()
}
</script>

<style lang="scss" scoped>
.main-title-color {
  color: #d14328;
}

.card-swiper {
  --wot-swiper-radius: 0;
  --wot-swiper-item-padding: 0 24rpx;
  --wot-swiper-nav-dot-color: #e7e7e7;
  --wot-swiper-nav-dot-active-color: #4d80f0;
  padding-bottom: 24rpx;
  :deep(.custom-indicator-class) {
    bottom: -16px;
  }
  :deep(.custom-image) {
    border-radius: 12rpx;
  }
  :deep(.custom-image-prev) {
    height: 168px !important;
  }
}

.truncate-text {
  display: -webkit-box;
  -webkit-line-clamp: 3; /* 显示的行数 */
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: normal;
}
</style>
