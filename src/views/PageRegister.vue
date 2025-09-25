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
  <!-- BEGIN register -->
  <div class="register">
    <!-- BEGIN register-content -->
    <div class="register-content">
      <form
        v-on:submit.prevent="submitForm()"
        method="POST"
        name="register_form"
      >
        <h1 class="text-center">회원가입</h1>
        <p class="text-inverse text-opacity-50 text-center">
          회원가입 후 5분이내 관리자의 승인 후 로그인이 가능합니다. 서버팀
          010-6722-8312
        </p>
        <div class="mb-3">
          <label class="form-label"
            >이름 <span class="text-danger">*</span></label
          >
          <input
            type="text"
            class="form-control form-control-lg bg-white bg-opacity-5"
            placeholder="셀러 가입은 업체명을 입력해 주세요"
            value=""
          />
        </div>
        <div class="mb-3">
          <label class="form-label"
            >이메일 주소 <span class="text-danger">*</span></label
          >
          <input
            type="text"
            class="form-control form-control-lg bg-white bg-opacity-5"
            placeholder="username@address.com"
            value=""
          />
        </div>
        <div class="mb-3">
          <label class="form-label"
            >비밀번호 <span class="text-danger">*</span></label
          >
          <input
            type="password"
            class="form-control form-control-lg bg-white bg-opacity-5"
            value=""
          />
        </div>
        <div class="mb-3">
          <label class="form-label"
            >비밀번호 확인 <span class="text-danger">*</span></label
          >
          <input
            type="password"
            class="form-control form-control-lg bg-white bg-opacity-5"
            value=""
          />
        </div>
        <!-- <div class="mb-3">
          <label class="form-label"
            >Country <span class="text-danger">*</span></label
          >
          <select class="form-select form-select-lg bg-white bg-opacity-5">
            <option>United States</option>
          </select>
        </div>
        <div class="mb-3">
          <label class="form-label"
            >Gender <span class="text-danger">*</span></label
          >
          <select class="form-select form-select-lg bg-white bg-opacity-5">
            <option>Female</option>
            <option>Male</option>
          </select>
        </div>
        <div class="mb-3">
          <label class="form-label"
            >Date of Birth <span class="text-danger">*</span></label
          >
          <div class="row gx-2">
            <div class="col-6">
              <select class="form-select form-select-lg bg-white bg-opacity-5">
                <option>Month</option>
                <option v-for="month in 12">
                  {{ month }}
                </option>
              </select>
            </div>
            <div class="col-3">
              <select class="form-select form-select-lg bg-white bg-opacity-5">
                <option>Day</option>
                <option v-for="day in 30">
                  {{ day }}
                </option>
              </select>
            </div>
            <div class="col-3">
              <select class="form-select form-select-lg bg-white bg-opacity-5">
                <option>Year</option>
                <template v-for="year in 2025">
                  <option v-if="year > 1950">
                    {{ year }}
                  </option>
                </template>
              </select>
            </div>
          </div>
        </div> -->
        <div class="mb-3">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value=""
              id="customCheck1"
            />
            <label class="form-check-label" for="customCheck1"
              >서비스에 필요한 <a href="#">개인정보</a> 와
              <a href="#">서비스 약과</a>에 동의 합니다.</label
            >
          </div>
        </div>
        <div class="mb-3">
          <button
            type="submit"
            class="btn btn-outline-theme btn-lg d-block w-100"
          >
            회원가입
          </button>
        </div>
        <div class="text-inverse text-opacity-50 text-center">
          이미 가입 하셨나요?
          <RouterLink to="/login">로그인</RouterLink>하러 가기
        </div>
      </form>
    </div>
    <!-- END register-content -->
  </div>
  <!-- END register -->
</template>