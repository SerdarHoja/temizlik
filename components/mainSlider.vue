<template>
  <div class="container mx-auto mt-4 lg:px-10 px-5">
    <a-carousel arrows>
      <div
        slot="prevArrow"
        slot-scope="props"
        class="custom-slick-arrow"
        style="left: 10px; z-index: 1"
      >
        <a-icon type="left-circle" />
      </div>
      <div
        slot="nextArrow"
        slot-scope="props"
        class="custom-slick-arrow"
        style="right: 10px"
      >
        <a-icon type="right-circle" />
      </div>
      <div>
        <img src="@/assets/img/1.jpeg" alt="" />
      </div>
      <div><img src="@/assets/img/2.jpeg" alt="" /></div>
      <div><img src="@/assets/img/3.jpeg" alt="" /></div>
    </a-carousel>
  </div>
</template>
<script>
export default {}
</script>
<style scoped>
.ant-carousel >>> .slick-slide {
  text-align: center;
  height: 600px;
  overflow: hidden;
}
@media only screen and (max-width: 768px) {
  .ant-carousel >>> .slick-slide {
    height: 200px;
  }
}
.ant-carousel >>> .custom-slick-arrow {
  width: 25px;
  height: 25px;
  font-size: 25px;
  color: #fff;
  background-color: rgba(31, 45, 61, 0.11);
  opacity: 0.3;
}
.ant-carousel >>> .custom-slick-arrow:before {
  display: none;
}
.ant-carousel >>> .custom-slick-arrow:hover {
  opacity: 0.5;
}

.ant-carousel >>> .slick-slide h3 {
  color: #fff;
}
</style>
