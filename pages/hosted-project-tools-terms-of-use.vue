<template>
  <PolicyViewer
    title="Hosted Project Tools Terms of Use"
    description="Sigstore is a Linux Foundation project. The Linux Foundation Projects Hosted Project Tools Terms of Use are displayed below."
    source-url="https://lfprojects.org/policies/hosted-project-tools-terms-of-use/"
  />
</template>

<script>
export default {
  name: "HostedProjectToolsTermsOfUsePage",
  head() {
    const siteUrl = process.env.VUE_APP_FRONTEND || "https://sigstore.dev";
    return {
      title: "Hosted Project Tools Terms of Use",
      titleTemplate: "%s · Sigstore",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Sigstore Hosted Project Tools Terms of Use"
        },
        {
          property: "og:title",
          content: "Hosted Project Tools Terms of Use · Sigstore"
        },
        {
          property: "og:description",
          content: "Sigstore Hosted Project Tools Terms of Use"
        },
        {
          name: "twitter:title",
          content: "Hosted Project Tools Terms of Use · Sigstore"
        },
        {
          name: "twitter:description",
          content: "Sigstore Hosted Project Tools Terms of Use"
        }
      ],
      link: [
        {
          rel: "canonical",
          href: `${siteUrl}/hosted-project-tools-terms-of-use`
        }
      ]
    };
  }
};
</script>
