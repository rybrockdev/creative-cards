<template>
  <div class="row">
    <div class="col-sm-6 card edit-area">
      <cc-text-input @displayTextChanged="textBoxValue1 = $event"></cc-text-input>
      <ccImageUpload @displayImageChanged="imageName = $event"></ccImageUpload>
      <hr />
      <cc-text-input @displayTextChanged="textBoxValue2 = $event"></cc-text-input>
      <cc-text-input @displayTextChanged="textBoxValue3 = $event"></cc-text-input>
      <ccSectionCompleted></ccSectionCompleted>
    </div>
    <div class="col-sm-6 card edit-display">
      <ccTextOutput :displayText="textBoxValue1" :containerHeight="130"></ccTextOutput>
      <cc-ImageOutput :displayImage="imageName" :containerHeight="350" :clearImageProp="clearImage"></cc-ImageOutput>
      <ccTextOutput :displayText="textBoxValue2" :containerHeight="130"></ccTextOutput>
      <ccTextOutput :displayText="textBoxValue3" :containerHeight="130"></ccTextOutput>
    </div>
  </div>
</template>

<script>
import TextInput from "./TextInput";
import TextOutput from "./TextOutput";
import ImageUpload from "./ImageUpload";
import ImageOutput from "./ImageOutput";
import SectionCompleted from "./SectionCompleted";

export default {
  data() {
    return {
      textBoxValue1: "",
      textBoxValue2: "",
      textBoxValue3: "",
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
    ccTextInput: TextInput,
    ccTextOutput: TextOutput,
    ccImageUpload: ImageUpload,
    ccImageOutput: ImageOutput,
    ccSectionCompleted: SectionCompleted
  }
};
</script>

<style>
.edit-area {
  background: #d2f9f9;
  padding: 20px;
  height: 800px;
}
.card-display {
  height: 800px;
  padding: 20px;
}
</style>