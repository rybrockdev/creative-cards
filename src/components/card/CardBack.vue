<template>
  <div class="row">
    <div class="col-sm-6 card edit-area">
      <ccImageUpload @displayImageChanged="imageName = $event"></ccImageUpload>
      <hr />
      <ccSectionCompleted></ccSectionCompleted>
    </div>
    <div class="col-sm-6 card edit-display">
      <cc-ImageOutput :displayImage="imageName" :containerHeight="400" :clearImageProp="clearImage"></cc-ImageOutput>
    </div>
  </div>
</template>

<script>
import ImageUpload from "./ImageUpload";
import ImageOutput from "./ImageOutput";
import SectionCompleted from "./SectionCompleted";

export default {
  data() {
    return {
      imageName: ""
    };
  },
  methods: {
    clearImage: function() {
      if (this.imageName != "") {
        this.imageName = "placeholder.png";
      }
    }
  },
  components: {
    ccImageUpload: ImageUpload,
    ccImageOutput: ImageOutput,
    ccSectionCompleted: SectionCompleted
  }
};
</script>

<style>
</style>