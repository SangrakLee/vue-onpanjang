<script>
import { useAppOptionStore } from "@/stores/app-option";
import { useRouter, RouterLink } from "vue-router";

const appOption = useAppOptionStore();

export default {
  mounted() {
    appOption.appSidebarHide = true;
    appOption.appHeaderHide = true;
    appOption.appContentClass = "p-0";
  },
  beforeUnmount() {
    appOption.appSidebarHide = false;
    appOption.appHeaderHide = false;
    appOption.appContentClass = "";
  },
  methods: {
    submitForm: function () {
      this.$router.push("/");
    },
  },
};
</script>
<template>
  <!-- BEGIN login -->
  <div class="login">
    <!-- BEGIN login-content -->
    <div class="login-content">
      <form v-on:submit.prevent="submitForm()" method="POST" name="login_form">
        <h1 class="text-center font-kr">LOGIN</h1>
        <div class="text-inverse text-opacity-50 text-center mb-4 font-kr">
          로그인을 위해 승인된 이메일로 접속해 주세요.
        </div>
        <div class="mb-3">
          <label class="form-label"
            >Email Address <span class="text-danger">*</span></label
          >
          <input
            type="text"
            class="form-control form-control-lg bg-white bg-opacity-5"
            value=""
            placeholder=""
          />
        </div>
        <div class="mb-3">
          <div class="d-flex">
            <label class="form-label"
              >Password <span class="text-danger">*</span></label
            >
            <a
              href="#"
              class="ms-auto text-inverse text-decoration-none text-opacity-50 font-kr"
              >비밀번호 찾기</a
            >
          </div>
          <input
            type="password"
            class="form-control form-control-lg bg-white bg-opacity-5"
            value=""
            placeholder=""
          />
        </div>
        <div class="mb-3">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value=""
              id="customCheck1"
            />
            <label class="form-check-label font-kr" for="customCheck1"
              >아이디 저장</label
            >
          </div>
        </div>
        <button
          type="submit"
          class="btn btn-outline-theme btn-lg d-block w-100 fw-500 mb-3 font-kr"
        >
          로그인
        </button>
        <div class="text-center text-inverse text-opacity-50 font-kr">
          가입 전이라면 회원가입 먼저 해 주세요.
          <RouterLink to="/register">회원가입</RouterLink>.
        </div>
      </form>
    </div>
    <!-- END login-content -->
  </div>
  <!-- END login -->
</template>