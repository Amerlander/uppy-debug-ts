<script>
 
    import { getContext } from 'svelte';
    import { Dashboard } from '@uppy/svelte';

    export let meta = '';

    const uppyDashID = "UppyDash" + Math.random().toString(16).slice(2);

    const {uppy} = getContext('uppyContext');

     uppy.on("file-added", (file) => {
         if(file.source!=uppyDashID) return;
         file.data.meta = meta;
         console.log(`File Added to Dashboard ${uppyDashID} with Metadata ${meta}`);
     });

</script>

<Dashboard uppy={uppy} plugins={["Webcam"]} props={{
		id:uppyDashID
}} />

<style lang="scss">

</style>