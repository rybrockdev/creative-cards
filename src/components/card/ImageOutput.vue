<template>
  <div
    class="imageContainer"
    :style="styleObject"
    @mouseover="showOptions = true"
    @mouseleave="showOptions = false"
  >
    <button
      type="button"
      class="btn btn-outline-danger btn-sm"
      v-show="showOptions"
      @click="clearImageProp"
    >remove image</button>
    <img id="outputImage" />
    {{ displayImage }}
  </div>
</template>

<script>
import firebase from "firebase";
export default {
  props: {
    displayImage: {
      type: String
    },
    containerHeight: {
      type: Number,
      default: 200
    },
    clearImageProp: Function
  },
  data() {
    return {
      showOptions: false
    };
  },
  watch: {
    displayImage: function() {
      var storageRef = firebase
        .storage()
        .ref("user_uploads/" + this.displayImage);
      storageRef.getDownloadURL().then(function(url) {
        var img = document.getElementById("outputImage");
        img.src = url;
        setDraggable();
      });
    }
  },
  computed: {
    styleObject: function() {
      return {
        height: this.containerHeight + "px"
      };
    }
  }
};
function setDraggable() {
  $("#outputImage").draggable();
}
</script>

<style>
.imageContainer {
  border: 1px dotted #000;
  overflow: hidden;
  margin: 5px 0;
}
button {
  position: absolute;
  z-index: 1;
}
img {
  width: 130%;
}
</style>