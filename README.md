<!DOCTYPE html>
<!--Will Mehler 2023-->
<!--Fix scroll issue and add email list and change.org link-->
<html>
<head>
	<title>Social Media Issues</title>
	<style>
		body {
			background-color: black;
			color: white;
			font-family: "Source Code Pro", monospace;
			font-size: 48px;
			text-align: center;
			margin-top: 100px;
			margin-bottom: 200vh; /* add margin to bottom of body */
		}

		.animate {
			overflow: hidden;
			border-right: 3px solid white;
			width: 0;
			display: inline-block;
			animation: typing 3s steps(20) forwards, blink-caret .75s step-end infinite;
			margin-right: 10px;
			letter-spacing: 1px;
		}

		@keyframes typing {
			from {
				width: 0;
			}
			to {
				width: 19ch;
			}
		}

		@keyframes blink-caret {
			from, to {
				border-color: transparent;
			}
			50% {
				border-color: white;
			}
		}

		.text-container {
			opacity: 0;
			margin-top: 70vh;
			font-size: 25px;
			line-height: 1.5;
			padding: 20px;
			animation: fadeIn 1s ease-in-out forwards;
			position: relative; /* add position and z-index to fix overlapping issue */
			z-index: 1;
		}

		.show {
			opacity: 1;
			margin-top: 0;
		}

		.hide {
			display: none;
		}

		@keyframes fadeIn {
			from {
				opacity: 0;
			}
			to {
				opacity: 1;
			}
		}
	</style>
</head>
<body>
	<div>
		<span class="animate" style="font-size: 64px;">/SocialMediaIssues</span>
	</div>
	<div class="text-container hide">
		<p>Social media is harming teen mental health. From curated content to the pressure to present a perfect image, it's a toxic environment that's linked to anxiety, depression, and even suicide.</p>
	</div>
	<div class="text-container hide">
		<p>This is a serious problem. Here's how you can help.</p>
	</div>

	<script>
		window.addEventListener('scroll', revealText);

		function revealText() {
			var text = document.querySelectorAll('.text-container');
			var position = text[0].getBoundingClientRect().top;
			var screenPosition = window.innerHeight / .1;

			if (position < screenPosition) {
				text[0].classList.remove('hide');
				text[0].classList.add('show');
				window.removeEventListener('scroll', revealText);
				setTimeout(function() {
					text[1].classList.remove('hide');
					text[1].classList.add('show');
					window.removeEventListener('scroll', revealText);
				}, 7000);
			}
		}
	</script>
</body>
</html>
