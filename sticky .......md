 $(window).on('scroll',function() {    
   var scroll = $(window).scrollTop();
   if (scroll < 245) {
    $(".header-middle").removeClass("scroll-header");
   }else{
    $(".header-middle").addClass("scroll-header");
   }
  });
  
  
    var nav_offset_top = $('header').height()+10; 
    /*-------------------------------------------------------------------------------
	  Navbar 
	-------------------------------------------------------------------------------*/

	//* Navbar Fixed  
    function navbarFixed(){
        if ( $('.menu-nav').length ){ 
            $(window).scroll(function() {
                var scroll = $(window).scrollTop();   
                if (scroll >= nav_offset_top ) {
                    $(".menu-nav").addClass("navbar_fixed");
                } else {
                    $(".menu-nav").removeClass("navbar_fixed");
                }
            });
        };
    };
    navbarFixed();