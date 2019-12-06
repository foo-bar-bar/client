<template>
  <div class="upload-img">
    <b-form class="basic">
    <b-form-file
      v-model="file"
      :state="Boolean(file)"
      placeholder="Choose a file or drop it here..."
    >
    </b-form-file>
    <br>
    <button type="submit" class="btn btn-primary" @click.prevent="uploadImage">Upload</button>
    </b-form>

  </div>
</template>

<script>
import axios from "../../apis/server"

export default {
  name: "uploadImage",
  methods: {
    uploadImage() {
      console.log(this.file)
      let fd = new FormData()

      fd.append("image", this.file)
      console.log(fd)
      axios({
        url: "/profile",
        method: "post",
        data: fd,
        headers: {
          token: localStorage.getItem("token")
        }
      })
        .then(({data}) => {
          console.log(data)
          this.$emit("refetch")
          
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  data() {
    return {
      file: null
    }
  }
}
</script>

<style>
  .upload-img {
    width: 25%;
    margin: 20vh auto 0 auto
  }

  .btn {
    margin: auto !important
  }

  .basic {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column
  }
</style>