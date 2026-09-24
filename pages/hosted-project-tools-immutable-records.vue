<template>
  <PolicyViewer
    title="Hosted Project Tools Immutable Record Notice"
    description="Sigstore is a Linux Foundation project. The Linux Foundation Projects Hosted Project Tools Immutable Record Notice is displayed below."
    source-url="https://lfprojects.org/policies/hosted-project-tools-immutable-records/"
  />
</template>

<script>
export default {
  name: "HostedProjectToolsImmutableRecordsPage",
  head() {
    const siteUrl = process.env.VUE_APP_FRONTEND || "https://sigstore.dev";
    return {
      title: "Hosted Project Tools Immutable Record Notice",
      titleTemplate: "%s · Sigstore",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Sigstore Hosted Project Tools Immutable Record Notice"
        },
        {
          property: "og:title",
          content: "Hosted Project Tools Immutable Record Notice · Sigstore"
        },
        {
          property: "og:description",
          content: "Sigstore Hosted Project Tools Immutable Record Notice"
        },
        {
          name: "twitter:title",
          content: "Hosted Project Tools Immutable Record Notice · Sigstore"
        },
        {
          name: "twitter:description",
          content: "Sigstore Hosted Project Tools Immutable Record Notice"
        }
      ],
      link: [
        {
          rel: "canonical",
          href: `${siteUrl}/hosted-project-tools-immutable-records`
        }
      ]
    };
  }
};
</script>
