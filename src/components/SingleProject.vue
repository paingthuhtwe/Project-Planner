<template>
  <div class="project">
    <div class="flexing">
      <div @click="showDetail = !showDetail">
        <h5>
          <b>{{ project.title }}</b>
        </h5>
      </div>
      <div class="text-gray">
        <i class="fas fa-trash"></i>
        <i class="fas fa-edit"></i>
        <i class="fas fa-check"></i>
      </div>
    </div>
    <div>
      <p v-if="showDetail">{{ project.detail }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["project"],
  data() {
    return {
      showDetail: false,
    };
  },
};
</script>

<style scoped>
@import url("https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css");
@import url("https://use.fontawesome.com/releases/v5.15.1/css/all.css");
.project {
  padding: 20px;
  background: #f2f2f2;
  margin: 10px;
  border-left: 5px solid red;
  border-radius: 5px;
}

h5 {
  cursor: pointer;
  color: indigo;
}
i {
  margin-left: 15px;
  cursor: pointer;
}
i:hover {
  color: #777;
}
.text-gray {
  color: #444;
}
.flexing {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>