<template>
  <div class="policy-page">
    <section class="policy-hero bg-pastel-orange pt-128 pb-48 border-b border-gray-light">
      <div class="container inner">
        <h1 class="text-gray-dark mb-16">{{ title }}</h1>
        <p class="text-17 text-gray-dark max-w-690 leading-26 mb-16">
          {{ description }}
        </p>
        <div class="flex items-center text-15 text-gray-dark">
          <span>Hosted by LF Projects, LLC.</span>
          <a
            :href="sourceUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="ml-8 underline font-medium hover:text-purple-light"
          >
            Open on lfprojects.org &nearr;
          </a>
        </div>
      </div>
    </section>

    <section class="policy-body bg-gray-greyBkg py-32 md:py-64">
      <div class="container">
        <div class="policy-frame-card">
          <div class="policy-frame-header">
            <span class="policy-frame-source truncate">
              Source: <span class="font-mono text-13">{{ sourceUrl }}</span>
            </span>
            <a
              :href="sourceUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="policy-frame-link"
            >
              Open in new tab &nearr;
            </a>
          </div>

          <div class="policy-iframe-wrapper">
            <div v-if="isLoading" class="policy-loading-overlay">
              <div class="policy-spinner" />
              <p class="text-15 text-gray-dark mt-16">Loading content from LF Projects...</p>
            </div>
            <iframe
              :src="sourceUrl"
              :title="title"
              class="policy-iframe"
              loading="lazy"
              @load="onFrameLoaded"
            />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "PolicyViewer",
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      default: ""
    },
    sourceUrl: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      isLoading: true
    };
  },
  mounted() {
    this.setHeaderColour({
      bg: "bg-pastel-orange",
      text: "text-gray-dark"
    });
  },
  methods: {
    ...mapActions("settings", ["setHeaderColour"]),
    onFrameLoaded() {
      this.isLoading = false;
    }
  }
};
</script>

<style lang="scss" scoped>
.policy-page {
  width: 100%;
}

.policy-frame-card {
  background: #ffffff;
  border: 1px solid #e9e9e9;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
}

.policy-frame-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 20px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #e9e9e9;
  font-size: 1.4rem;
}

.policy-frame-source {
  color: #444444;
  margin-right: 16px;
}

.policy-frame-link {
  color: #6349ff;
  font-weight: 500;
  text-decoration: underline;
  white-space: nowrap;

  &:hover {
    color: #2a1e71;
  }
}

.policy-iframe-wrapper {
  position: relative;
  width: 100%;
  height: 80vh;
  min-height: 700px;
  background-color: #ffffff;
}

.policy-loading-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 10;
}

.policy-spinner {
  width: 40px;
  height: 40px;
  border: 3px solid #e9e9e9;
  border-top-color: #6349ff;
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

.policy-iframe {
  width: 100%;
  height: 100%;
  border: 0;
  display: block;
}

@media (max-width: 768px) {
  .policy-iframe-wrapper {
    height: 70vh;
    min-height: 500px;
  }

  .policy-frame-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }
}
</style>
