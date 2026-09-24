<template>
  <PolicyViewer
    title="Privacy Policy"
    description="Sigstore is a Linux Foundation project. The Linux Foundation Projects Privacy Policy is displayed below."
    source-url="https://lfprojects.org/policies/privacy-policy/"
  />
</template>

<script>
export default {
  name: "PrivacyPolicyPage",
  head() {
    const siteUrl = process.env.VUE_APP_FRONTEND || "https://sigstore.dev";
    return {
      title: "Privacy Policy",
      titleTemplate: "%s · Sigstore",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Sigstore Privacy Policy"
        },
        { property: "og:title", content: "Privacy Policy · Sigstore" },
        {
          property: "og:description",
          content: "Sigstore Privacy Policy"
        },
        { name: "twitter:title", content: "Privacy Policy · Sigstore" },
        {
          name: "twitter:description",
          content: "Sigstore Privacy Policy"
        }
      ],
      link: [
        {
          rel: "canonical",
          href: `${siteUrl}/privacy-policy`
        }
      ]
    };
  }
};
</script>
