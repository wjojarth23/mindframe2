
<script>// IMAGE SLIDES & CIRCLES ARRAYS, & COUNTER
	var imageSlides = document.getElementsByClassName('imageSlides');
	var circles = document.getElementsByClassName('circle');
	var leftArrow = document.getElementById('leftArrow');
	var rightArrow = document.getElementById('rightArrow');
	var counter = 0;
	
	// HIDE ALL IMAGES FUNCTION
	function hideImages() {
	  for (var i = 0; i < imageSlides.length; i++) {
		imageSlides[i].classList.remove('visible');
	  }
	}
	
	// REMOVE ALL DOTS FUNCTION
	function removeDots() {
	  for (var i = 0; i < imageSlides.length; i++) {
		circles[i].classList.remove('dot');
	  }
	}
	
	// SINGLE IMAGE LOOP/CIRCLES FUNCTION
	function imageLoop() {
	  var currentImage = imageSlides[counter];
	  var currentDot = circles[counter];
	  currentImage.classList.add('visible');
	  removeDots();
	  currentDot.classList.add('dot');
	  counter++;
	}
	
	// LEFT & RIGHT ARROW FUNCTION & CLICK EVENT LISTENERS
	function arrowClick(e) {
	  var target = e.target;
	  if (target == leftArrow) {
		clearInterval(imageSlideshowInterval);
		hideImages();
		removeDots();
		if (counter == 1) {
		  counter = (imageSlides.length - 1);
		  imageLoop();
		  imageSlideshowInterval = setInterval(slideshow, 10000);
		} else {
		  counter--;
		  counter--;
		  imageLoop();
		  imageSlideshowInterval = setInterval(slideshow, 10000);
		}
	  } 
	  else if (target == rightArrow) {
		clearInterval(imageSlideshowInterval);
		hideImages();
		removeDots();
		if (counter == imageSlides.length) {
		  counter = 0;
		  imageLoop();
		  imageSlideshowInterval = setInterval(slideshow, 10000);
		} else {
		  imageLoop();
		  imageSlideshowInterval = setInterval(slideshow, 10000);
		}
	  }
	}
	
	leftArrow.addEventListener('click', arrowClick);
	rightArrow.addEventListener('click', arrowClick);
	
	
	// IMAGE SLIDE FUNCTION
	function slideshow() {
	  if (counter < imageSlides.length) {
		imageLoop();
	  } else {
		counter = 0;
		hideImages();
		imageLoop();
	  }
	}
	
	// SHOW FIRST IMAGE, & THEN SET & CALL SLIDE INTERVAL
	setTimeout(slideshow, 1000);
	var imageSlideshowInterval = setInterval(slideshow, 10000);
</script>
<img src="src/lib/images/2.ExtFront_02_ZK (12.jpg" class="bgimg"/>
<div class="menubox"><svg
   width="100mm"
   height="60mm"

   class="logo"
   viewBox="0 0 100 60"
   xmlns="http://www.w3.org/2000/svg">
  <path
     id="path70"
     style="fill:#ffffffff;fill-opacity:1;stroke-width:0.992658;-inkscape-stroke:none"
     d="m 39.172298,5.4498343e-4 c -1.793475,0 -3.332094,0.64846267657 -4.599905,1.93963391657 -1.267815,1.29116 -1.90478,2.8606078 -1.90478,4.6870942 0,1.8265242 0.636965,3.3932899 1.90478,4.6844499 1.20442,1.226623 2.653912,1.872203 4.333474,1.93381 H 30.801603 V 0.00158783 h -1.07964 V 11.871786 L 21.052032,0.00158783 H 19.62643 V 13.245513 H 16.858732 V 13.169297 0.00159807 h -1.07964 V 13.245513 H 13.012886 V 0.00158783 H 11.587283 L 6.5062124,6.9559944 1.425639,0.00158783 H 3.538641e-5 C -3.5898978e-4,20.001054 0.0026325,40.000532 0.00455629,60 H 44.852884 v -9.331837 h 4.669992 V 60 h 1.035898 v -9.331837 h 4.667511 V 60 H 100 V 0 Z m 0,1.09949791657 h 3.589357 V 12.151827 h -3.589357 c -1.50438,0 -2.776259,-0.537638 -3.833421,-1.620424 -1.063203,-1.0766391 -1.591624,-2.3720504 -1.591624,-3.9041504 0,-1.5320601 0.528304,-2.831822 1.591624,-3.9147307 1.057124,-1.0765831 2.328932,-1.612479 3.833421,-1.612479 z m 4.670986,0.00154 h 5.679545 v 9.3297181 h 1.035898 V 1.1015795 h 4.66751 v 9.3297185 h 1.035891 V 10.347092 1.1084205 H 98.959636 V 58.889279 l -42.697508,0.002 V 49.566374 H 43.840301 V 48.80142 H 56.262128 V 47.349347 L 49.734582,42.18528 56.262128,37.020692 V 35.568618 H 43.840301 V 35.257875 L 56.262128,29.661838 V 28.478681 L 43.840301,22.882654 v -0.03975 l 5.682528,-4.488584 v 0.810478 c 0,0.984218 0.329888,1.834761 0.986688,2.533067 0.656804,0.698316 1.456281,1.051869 2.381969,1.051869 0.925688,0 1.725161,-0.353553 2.38197,-1.051869 0.6568,-0.698306 0.988672,-1.548849 0.988672,-2.533067 v -7.78235 H 56.183061 43.843245 Z M 1.081665,1.3710318 6.5062124,8.8114068 11.931256,1.381619 V 13.245513 H 1.081665 Z m 19.624405,0.0085 8.667446,11.8659572 H 20.70607 Z M 43.843284,12.484247 h 5.679545 v 4.493347 l -5.682528,4.488574 v -8.214324 h 0.003 z m 6.715443,0 h 4.66751 v 6.680728 c 0,0.689169 -0.226439,1.266554 -0.686955,1.750114 v 0.002 c -0.454832,0.489625 -0.999583,0.731067 -1.647796,0.731067 -0.648213,0 -1.193494,-0.243307 -1.654256,-0.733187 -0.454741,-0.483479 -0.678503,-1.0607 -0.678503,-1.750114 z M 1.0453786,14.356122 H 42.799432 V 58.891481 H 1.0453786 Z m 42.7949224,9.719349 3.486961,1.56483 v 6.860183 l -3.486961,1.567483 z m 4.524847,2.038094 6.57229,2.96133 -6.57229,2.952325 z m -4.524847,10.558931 h 11.129447 l -6.985854,5.512918 6.977399,5.514515 H 43.840301 Z" />
</svg>
<button class="menu"
		><svg
			xmlns="http://www.w3.org/2000/svg"
			width="48"
			height="48"
			viewBox="0 0 24 24"
			fill="none"
			stroke="#ffffff"
			stroke-width="2"
			stroke-linecap="butt"
			stroke-linejoin="round"
			><line x1="3" y1="12" x2="21" y2="12"></line><line x1="3" y1="6" x2="21" y2="6"></line><line
				x1="3"
				y1="18"
				x2="21"
				y2="18"
			></line></svg
		></button
	>
</div>

  
	<div class="vertical" style="top: -0px;
	left: -46px;">MINDFRAME</div><div class="vertical"style="top: 120vh;
	left: -46px; font-size: 17vh; white-space: nowrap;">142 KELLOGG</div>
	<span id ="leftArrow" class="slideshowArrow">&#8249;</span>
	<span id ="rightArrow" class="slideshowArrow">&#8250;</span>
	
	<div class="slideshowCircles">
  <!-- Filled 'dot' class is set to first image in slideshow, and then via Javascript the filled 'dot' class follows the current image.
  Make sure you match the number of these 'circle' span elements to the number of images in your slideshow. -->
	  <span class="circle dot"></span>
	  <span class="circle"></span>
	  <span class="circle"></span>
	</div>
<style>
	@font-face {
    font-family: CCCulture;
    src: url("src/lib/fonts/Cookie Cutter Culture.otf") format("opentype");
}

	.vertical {
		writing-mode: vertical-rl;
		text-orientation: mixed;
		font-size: 19vh;
		position: absolute;
    color:white;
	font-family: CCCulture;
	font-weight: 500;
		
	}
	.slideshowContainer {
  position: relative;
  overflow: hidden;
  margin: 50px 0 75px;
  width: 100%;
  height: 100vh;
}

.imageSlides {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  min-width: 100%;
  min-height: 100%;
  opacity: 0;
  transition: opacity 1s ease-in-out;
  z-index: -1;
}

/* add 'visible' class via Javascript */
.visible {
  opacity: 1;
}

.slideshowArrow {
  font-size: 7em;
  color: rgba(255, 255, 255, 0.5);
  cursor: pointer;
  transition: opacity 0.2s ease-in-out;
}

.slideshowArrow:hover {
  opacity: 0.75;
}

#leftArrow {
  position: absolute;
  left: 4%;
  top: 50%;
  transform: translate(-50%, -50%);
}

#rightArrow {
  position: absolute;
  right: 4%;
  top: 50%;
  transform: translate(50%, -50%);
}

.slideshowCircles {
  position: absolute;
  bottom: 2%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.circle {
  display: inline-block;
  margin-left: 3px;
  margin-right: 3px;
  width: 15px;
  height: 15px;
  transition: 1s ease-in-out;
  background-color: rgba(255, 255, 255, 0.5);
}

.dot {
  background-color: rgba(255, 255, 255, 0.7);
  width: 30px;

}
	.bgimg{
        z-index: -1;      
		height: 100vh;
		//object-position:bottom;
		min-width: 100vw;
		object-fit: cover;  
		position:fixed;
    }
    .logo{
      width:100px;
      height:60px;
    }
	.menubox {
position: fixed;
top:0px;
padding:10px;
right:0px;
	}
    .menu{
      position: relative;
      right:-55px;
    }
</style>
