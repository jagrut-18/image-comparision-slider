<script>
	let mousePosition = 0;

	function handleMousemove(event) {
		var rect = event.target.getBoundingClientRect();
		mousePosition = event.clientX - rect.left;
		const outputImage = document.getElementById("output-image");
		outputImage.style.clip = `rect(0px, ${mousePosition}px, 450px, 0px)`;
	}
</script>

<div class="images-container" on:mousemove={handleMousemove}>
		<img 
id="input-image"		 src="https://pixabay.com/get/gdcb2720bf31bbe5a66e43ac7ec64b1419766a9f4da0458e77dcd73dc064f8e0b15496a5e9aacb92357aa26b27619769f_640.jpg" alt=""/>
<img 
id="output-image"		 src="https://pixabay.com/get/g6e59cbaec8f2eafa7c53d7819a01a1b44d7e050d1cc511186f5a3a6d1bd6b0c8ea1407bdbf07d3a26d38e3222ca2db36_640.jpg" alt=""/>
</div>

<style>
	.images-container {
		cursor: grabbing;
	}

	#output-image {
		position: absolute;
		z-index: 10;
		top: 0;
		left: 0;
	}
</style>