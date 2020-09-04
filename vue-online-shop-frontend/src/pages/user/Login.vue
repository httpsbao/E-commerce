<template>
  <div id="login-form"></div>
</template>

<script>
export default {
  data() {
    return {
      model: { manufacturer: { name: "", _id: "" } }
    };
  },
  mounted() {
    const appId = "";
    const userPoolId = "5f2fb555d9365ada50ef39e0";
    const domain = "https://E-commerce.authing.co";

    const form = new Guard(userPoolId, {
      //logo: "@/assets/xun.png",
      // logo: "https://tuture.co/images/avatar.png",
      title: "迷你电商",
      mountId: "login-form",
      hideClose: true
    });

    const that = this;

    form.on("authenticated", userInfo => {
      that.$store.commit("SET_USER", userInfo);
      localStorage.setItem("token", JSON.stringify(userInfo.token));
      localStorage.setItem("userInfo", JSON.stringify(userInfo));

      that.$router.push("/");
    });
  }
};
</script>
