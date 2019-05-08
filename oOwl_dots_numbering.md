// way one
var i = 1;
$('.owl-carousel .owl-dot').each(function(){
  $(this).text(i);
  i++;
});


//way two
var dot = $('.slideWrap .owl-dot');
dot.each(function() {
	var index = $(this).index() + 1;
  if(index < 10){
  	$(this).html('0').append(index);
  }else{
     $(this).html(index);
  }
});