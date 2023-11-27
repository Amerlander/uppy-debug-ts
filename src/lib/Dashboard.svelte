<script>
 
    import { getContext } from 'svelte';
    import { Dashboard } from '@uppy/svelte';

    const uppyDashID = "UppyDash" + Math.random().toString(16).slice(2);

    const {uppy} = getContext('uppyContext');

     uppy.on("file-added", (file) => {
         console.log('File Added', file);
         if(file.source!=uppyDashID) return;
         console.log(`File Added to Dashboard ${uppyDashID}`);
     });

    function handleFileAdded(file) {
        console.log(`File Added to Dashboard ${uppyDashID}`);
    }
    
</script>

<Dashboard uppy={uppy} plugins={["Webcam"]} props={{
		id:uppyDashID
}} />

<style lang="scss">

</style>