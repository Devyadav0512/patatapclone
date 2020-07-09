<!DOCTYPE html>
<html>
<head>
	<title>Patatap Clone</title>	
	<script type="text/javascript" src="assets/js/lib/paper-full.js"></script>
	<style type="text/css">
		canvas{
			width: 100%;
			height: 100%;
		}
		body,html{
			height: 100%;
			margin:0;
		}
	</style>
	<script type="text/javascript" src="assets/js/lib/howler.js"></script>
	<script type="text/paperscript" canvas="myCanvas">
		var col = ["#1abc9c","#2ecc71","#3498db","#9b59b6","#34495e","#16a085","#27ae60","#2980b9","#8e44ad","#2c3e50","#f1c40f","#e67e22","#e74c3c","#95a5a6","#f39c12","#d35400","#1abc9c","#2ecc71","#3498db","#9b59b6","#34495e","#16a085","#27ae60","#2980b9","#8e44ad","#2c3e50",];

		var soun = ["sounds/bubbles.mp3","sounds/clay.mp3","sounds/confetti.mp3","sounds/corona.mp3","sounds/dotted-spiral.mp3","sounds/flash-1.mp3","sounds/flash-2.mp3","sounds/flash-3.mp3","sounds/glimmer.mp3","sounds/moon.mp3","sounds/pinwheel.mp3","sounds/piston-1.mp3","sounds/piston-2.mp3","sounds/prism-1.mp3","sounds/prism-2.mp3","sounds/prism-3.mp3","sounds/splits.mp3","sounds/squiggle.mp3","sounds/strike.mp3","sounds/suspension.mp3","sounds/timer.mp3","sounds/ufo.mp3","sounds/veil.mp3","sounds/wipe.mp3","sounds/zig-zag.mp3","sounds/moon.mp3"];

		var alpha = ["a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z"];

		var circles = [];

		function onKeyDown(event){
		var alp = event.key;
		var sun = soun[alpha.indexOf(alp)];
		var colo = col[alpha.indexOf(alp)];
		var vvv = {src:[sun]};
		vvv.src.push(sun);
		var maxPoint = new Point(view.size.width,view.size.height);
		var randomPoint = Point.random();
		var point = maxPoint * randomPoint;
		var circ = new Path.Circle(point, 500);
		circ.fillColor = colo;
		circles.push(circ);
		new Howl(vvv).play();
		}		
		

	    function onFrame(event){
	    for(var i = 0; i < circles.length; i++){
        circles[i].fillColor.hue += 1;
	    circles[i].scale(0.9);
	    }	    
	    }

	</script>
</head>
<body>
	<canvas id="myCanvas" resize style="background:black"></canvas>
</body>
</html>
