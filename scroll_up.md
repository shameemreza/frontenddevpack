<!--Scroll to top-->
	<div class="scroll-to-top scroll-to-target" data-target="html"><span class="fa fa-angle-up"></span></div>
  
  //Update Header Style and Scroll to Top
	function headerStyle() {
		if($('.main-header').length){
			var windowpos = $(window).scrollTop();
			var siteHeader = $('.main-header');
			var scrollLink = $('.scroll-to-top');
			if (windowpos >= 1) {
				siteHeader.addClass('fixed-header');
				scrollLink.fadeIn(300);
			} else {
				siteHeader.removeClass('fixed-header');
				scrollLink.fadeOut(300);
			}
		}
	}
	
	headerStyle();
	
	
	
	style 2
	--------
<a class="page-scroll-up show" id="page-scroll-up"><i class="ion-android-arrow-up"></i></a>
function scrollToTop() {
	if ( $insight.scroll_top_enable != 1 ) {
		return;
	}
	var $scrollUp = $( '#page-scroll-up' );
	var lastScrollTop = 0;
	var autoHide;

	$window.scroll( function() {
		clearTimeout( autoHide );

		var st = $( this ).scrollTop();
		if ( st > lastScrollTop ) {
			$scrollUp.removeClass( 'show' );
		} else {
			if ( $window.scrollTop() > 200 ) {
				$scrollUp.addClass( 'show' );

				autoHide = setTimeout( function() {
					$scrollUp.removeClass( 'show' );
				}, 6000 );
			} else {
				$scrollUp.removeClass( 'show' );
			}
		}
		lastScrollTop = st;
	} );

	$scrollUp.on( 'click', function( evt ) {
		$( 'html, body' ).animate( {scrollTop: 0}, 600 );
		evt.preventDefault();
	} );
}
  
  css
  -----------
  .page-scroll-up {
	position: fixed;
	right: 30px;
	bottom: -60px;
	z-index: 999;
	box-shadow: 0 30px 50px rgba(0, 0, 0, 0.03);
	display: block;
	padding: 0;
	width: 60px;
	height: 60px;
	border-radius: 50%;
	text-align: center;
	font-size: 25px;
	line-height: 60px;
	cursor: pointer;
	opacity: 0;
	visibility: hidden;
}
.page-scroll-up.show {
	bottom: 30px;
	opacity: 1;
	visibility: visible;
}