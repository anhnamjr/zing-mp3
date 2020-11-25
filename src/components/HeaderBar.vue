<template>
  <!-- <div class="header-bar">
      <div class="logo">
          <router-link to="/">
            <img src="https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/logo-mp-3.svg" width="100px" height="32px">
          </router-link>
      </div>
      <div class="search"></div>
      <div class="login"></div>
  </div> -->
  <b-container class="header-bar">
    <b-row>
      <b-col>
        <router-link to="/">
          <img
            src="https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/logo-mp-3.svg"
            width="100px"
            height="38px"
          />
        </router-link>
      </b-col>
      <b-col cols="8">
        <b-form-group id="search-form">
					<i class="fa fa-search"/>
					<b-form-input id="search" placeholder="Search..."></b-form-input>
				</b-form-group>
      </b-col>
      <b-col class="user-profile-container">

			</b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "header-bar",
};
</script>

<style>
.header-bar {
  /* border: 1px solid #000; */
  padding: 15px 15px 15px 0;
}
#search {
	padding-left: 35px;
	width: 100%;
	border-radius: 40px;
}

#search:focus{
	border: none;
	outline: none;
}

#search-form i{
	position: absolute;
	top: 12px;
	left: 25px;
}

</style>
