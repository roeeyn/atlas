<template>
  <div class="row">
    <div
      v-for="item in communities"
      class="col-md-4 col-xs-12 mb-4"
      :key="item.id"
    >
      <div class="card h-100 shadow px-2 px-lg-3 card-span pt-4">
        <div class="card-body">
          <h5 class="fw-bold lh-base fs-1 text-700"></h5>
          <div class="d-flex align-items-center">
            <g-link :to="item.node.path">
              <g-image :src="item.node.image" class="me-3 me-md-3" />
            </g-link>
            <div class="my-3">
              <p class="mb-0 text-black fw-bold">{{ item.node.title }}</p>
              <p class="fw-normal mb-0">
                 <font-awesome :icon="['fas', 'map-marker-alt']"/>
                {{ item.node.location }}
              </p>
            </div>
          </div>
          <div class="d-flex align-items-center mt-4 fs--1">
            <div class="tagcloud">
              <!-- only show 3 tags -->
              <g-link
                :to="item.path"
                v-for="item in item.node.tags.slice(0, 3)"
                :key="item.id"
              >
                {{ item.title }}
              </g-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    communities: Array,
  },
};
</script>
<style lang="scss" scoped></style>
