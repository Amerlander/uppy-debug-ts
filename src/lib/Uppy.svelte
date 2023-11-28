<script>
  import { browser } from '$app/environment';
  import { setContext } from 'svelte';

  import Uppy from '@uppy/core';
  import Webcam from '@uppy/webcam';

  import '@uppy/core/dist/style.css';
  import '@uppy/dashboard/dist/style.css';
  import '@uppy/webcam/dist/style.css';

  const uppy = (browser) ? new Uppy({debug: true})
      .use(Webcam)
      .on('files-added', (file) => {
        console.log("TUS File Added", file)
      }) : undefined;

  setContext('uppyContext', {uppy});

</script>

<slot />

<style>

.files-container {
  position: fixed;
  bottom: 0px;
  right: 0px;
  display: flex;
  z-index: 991;
  background: transparent;
  border-radius: 27px;
  padding: 5px;
  height: 50px;
  align-items: center;
  opacity: 0;
  pointer-events: none;
  transition: opacity .3s ease-in-out;
}

.visible {
  opacity: 1;
  pointer-events: initial;
}
.file {
  display: flex;
}
</style>