<template>
  <div class="row">
    <div class="col-sm-6 card edit-area">
      <cc-text-input @displayTextChanged="textBoxValue1 = $event"></cc-text-input>
      <ccSectionCompleted></ccSectionCompleted>
    </div>
    <div class="col-sm-6 card edit-display">
      <ccTextOutput :displayText="textBoxValue1" :containerHeight="750"></ccTextOutput>
    </div>
  </div>
</template>

<script>
import TextInput from "./TextInput";
import TextOutput from "./TextOutput";
import SectionCompleted from "./SectionCompleted";

export default {
  data() {
    return {
      textBoxValue1: ""
    };
  },
  components: {
    ccTextInput: TextInput,
    ccTextOutput: TextOutput,
    ccSectionCompleted: SectionCompleted
  }
};
</script>

<style>
</style>