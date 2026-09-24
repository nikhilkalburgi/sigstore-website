<template>
  <PolicyViewer
    title="Terms of Use"
    description="Sigstore is a Linux Foundation project. The Linux Foundation Projects Terms of Use are displayed below."
    source-url="https://lfprojects.org/policies/terms-of-use/"
  />
</template>

<script>
export default {
  name: "TermsOfUsePage",
  head() {
    const siteUrl = process.env.VUE_APP_FRONTEND || "https://sigstore.dev";
    return {
      title: "Terms of Use",
      titleTemplate: "%s · Sigstore",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Sigstore Terms of Use"
        },
        { property: "og:title", content: "Terms of Use · Sigstore" },
        {
          property: "og:description",
          content: "Sigstore Terms of Use"
        },
        { name: "twitter:title", content: "Terms of Use · Sigstore" },
        {
          name: "twitter:description",
          content: "Sigstore Terms of Use"
        }
      ],
      link: [
        {
          rel: "canonical",
          href: `${siteUrl}/terms-of-use`
        }
      ]
    };
  }
};
</script>
