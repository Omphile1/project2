<template>
  <div>
    <router-view></router-view>
    <div class="section"></div>
      <div class="container"></div>
        <simple-upload/>
  </div>
</template>
<script>

import SimpleUpload from './components/SimpleUpload';
export default {
  name:"App",
  component:{SimpleUpload}
}
</script>

