<template>
  <b-container class="header-bar">
    <b-row>
      <b-col cols="2">
        <router-link to="/">
          <img
            src="https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/logo-mp-3.svg"
            width="100px"
            height="38px"
          />
        </router-link>
      </b-col>
      <b-col cols="6" class="d-flex">
        <b-form-group id="search-form" class="flex-grow-1 align-self-end">
          <i class="fa fa-search" />
          <b-form-input id="search" placeholder="Search..."></b-form-input>
        </b-form-group>
      </b-col>
      <b-col cols="4" class="user-profile-container d-flex justify-content-end align-items-center">
        <b-button><i class="fas fa-upload"></i></b-button>
        <b-button><i class="far fa-bell"></i></b-button>
        <b-button><i class="fas fa-user-alt"></i></b-button>
        <router-link to="/" class="login-btn"><b>Đăng Nhập</b></router-link>
        <span class="setting">
          <b-button><i class="fa fa-arrow-down"></i></b-button>
          <!-- <div class="setting-dropdown">

          </div> -->
        </span>
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

#search:focus {
  border: none;
  outline: none;
}

#search-form {
  margin-bottom: 0;
}

#search-form i {
  position: absolute;
  top: 12px;
  left: 25px;
  color: #777;
}

.user-profile-container{
  padding: 0;
}

.user-profile-container button {
  margin: 0 5px;
  border-radius: 50%;
  background: #fff;
  color: #777;
  outline: 0;
}

.login-btn {
  border: none;
  color: #777;
}

.login-btn:hover{
  color: #6e55b4;
  text-decoration: none;
}

.setting-dropdown {
  border: 1px solid #ccc;
}
</style>
