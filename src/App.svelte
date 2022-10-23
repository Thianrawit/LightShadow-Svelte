<script>
	let p = {x:0, y:0}
	let windowW
	let windowH
	let shadowX
	let shadowY

	document.addEventListener('mousemove', function(e){
		p.x = (e.clientX - 17);
		p.y = (e.clientY - 10);

		windowW = window.innerWidth
		windowH = window.innerHeight
 
		shadowX = ((p.x / (windowW / 20.7)) - 10) * -3
		shadowY = ((p.y / (windowH / 19.7)) - 10) * -3
	})


</script>

<main>
	<!-- <div class="debug">
		<div class="textDebug">
			<p>x = {p.x} <br> y = {p.y}</p>
			<p>Window size = {windowW} * {windowH}</p>
			<p>Center = {(windowW /2) - 23} * {(windowH/2) - 5}</p>
			
			<p>Mouse = {p.x} * {p.y} <br> 
			Shadow = {shadowX} * {shadowY}</p>
				
			<p></p>
		</div>
	
		<div class="dummy" style="
					transform: translateX({(windowW /2) - 23}px) translateY({(windowH/2) - 5}px);
		"></div>
	</div> -->
	
	<div class="deg" id="cursor" style="left:{p.x}px; top:{p.y}px;"></div>
	<div class="circle" style="
		box-shadow: {shadowX}px {shadowY}px 30px rgba(0,0,0,0.15),
					{shadowX * -1}px {shadowY * -1}px 30px rgba(255,255,255,0.35);
	"></div>
</main>

<style>
	:global(body){
		width: 100%;
		height: 100vh;
		background: #afe3fd;
		display: flex;
		align-items: center;
		justify-content: center; 
		cursor: none;

		overflow: hidden;
	}

	.textDebug{
		position:fixed;
	}

	.circle{
		width: 15vw;
		height: 15vw;
		background: #daf3ff;

		border-radius: 20%;
	}

	.deg{
		width: 6vw;
		height: 6vw;
		background: rgba(255, 255, 255, 0.45);
		backdrop-filter: blur(0.5em);

		box-shadow: 0px 0px 50px rgba(255,255,255,1),
					0px 0px 60px rgba(255, 228, 49, 0.05);

		border-radius: 50%;

		position: absolute;
	}

	.dummy{
		background: #000;
		position: absolute;
		width: 1em;
		height: 1em;
	}
</style>