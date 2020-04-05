<template>
  <div class="row">
    <div class="col-sm-6 card edit-area">
      <cc-text-input @displayTextChanged="textBoxValue1 = $event"></cc-text-input>
      <cc-text-input @displayTextChanged="textBoxValue2 = $event"></cc-text-input>
      <cc-text-input @displayTextChanged="textBoxValue2 = $event"></cc-text-input>
      <ccSectionCompleted></ccSectionCompleted>
    </div>
    <div class="col-sm-6 card edit-display">
      <ccTextOutput :displayText="textBoxValue1" :containerHeight="240"></ccTextOutput>
      <ccTextOutput :displayText="textBoxValue2" :containerHeight="240"></ccTextOutput>
      <ccTextOutput :displayText="textBoxValue3" :containerHeight="240"></ccTextOutput>
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
      textBoxValue1: "",
      textBoxValue2: "",
      textBoxValue3: ""
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