function mainSlider() {
        var BasicSlider = $('.slider-active');
        BasicSlider.on('init', function(e, slick) {
            var $firstAnimatingElements = $('.single-slider:first-child').find('[data-animation]');
            doAnimations($firstAnimatingElements);
        });
        BasicSlider.on('beforeChange', function(e, slick, currentSlide, nextSlide) {
            var $animatingElements = $('.single-slider[data-slick-index="' + nextSlide + '"]').find('[data-animation]');
            doAnimations($animatingElements);
        });
        BasicSlider.slick({
            autoplay: false,
            autoplaySpeed: 10000,
            dots: false,
            fade: true,
			arrows: false,
            responsive: [
                { breakpoint: 767, settings: { dots: false, arrows: false } }
            ]
        });

        function doAnimations(elements) {
            var animationEndEvents = 'webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend';
            elements.each(function() {
                var $this = $(this);
                var $animationDelay = $this.data('delay');
                var $animationType = 'animated ' + $this.data('animation');
                $this.css({
                    'animation-delay': $animationDelay,
                    '-webkit-animation-delay': $animationDelay
                });
                $this.addClass($animationType).one(animationEndEvents, function() {
                    $this.removeClass($animationType);
                });
            });
        }
    }
    mainSlider();
    
    
    // css button
    .slider-active button.slick-arrow {
	position: absolute;
	top: 50%;
	left: 30px;
	transform: translateY(-50%);
	background: none;
	border: 0;
	background: #fff;
	width: 80px;
	font-size: 27px;
	padding: 0;
	color: #444;
	z-index: 9;
	border-radius:30px
}
.slider-active button.slick-next{left: auto;right:30px}

// dots
.slider-active .slick-dots {
	text-align: center;
	bottom: 30px;
	z-index: 99;
	position: absolute;
	left: 0;
	right: 0;
}
.slider-active .slick-dots li {
	display: inline-block;
	margin: 0 4px
}
.slider-active .slick-dots li button {
	background: no-repeat;
	border: 0;
	height: 10px;
	width: 5px;
	text-indent: -9999px;
	background: #fff;
	transition: .3s;
	padding: 0;
}
.slider-active .slick-dots li.slick-active button{height: 15px}