
<script >
	import Dashboard from '$lib/Dashboard.svelte';
</script>

<p>
Depending on which Dashboard is used the file gets a different Metadata applied.
But this does not work, when the file is Captured by the Webcam.
</p>

	Dashboard A
    <Dashboard meta={"A"} />

<br>
	
	Dashboard B
	<Dashboard meta={"B"} />
