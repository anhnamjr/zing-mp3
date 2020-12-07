<template>
  <b-container>
    <hr />
    <div class="footer-bar mt-5 mb-5">
      <img src="https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/logo-mp-3.png" width="40px" height="40px">
      <span>Một sản phẩm của Zalo</span>
      <div>
        <ul>
          <li><a href="#">Giới thiệu</a></li>•
          <li><a href="#">Liên hệ</a></li>•
          <li><a href="#">Quảng cáo</a></li>•
          <li><a href="#">Góp ý</a></li>•
          <li><a href="#">Thỏa thuận sử dụng</a></li>
        </ul>
      </div>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "footer-bar"
}
</script>

<style>
.footer-bar{
  text-align: center;
  color: #888 !important;
}
.footer-bar ul {
  list-style: none;
  display: flex;
  justify-content: center;
  margin: 10px auto;
}

.footer-bar li {
  margin: 0 5px;
}

.footer-bar li a{
  color: #888 !important;
}

.footer-bar li a:hover{
  color: #6e55b4 !important;
  text-decoration: none;
}
</style>