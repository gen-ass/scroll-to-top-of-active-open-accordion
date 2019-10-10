# Scroll to top of active open accordion
This code allows you to scroll to the top of an active accordion (open). Useful if you have a lot of elements that you need to scroll through.

# Sources:

https://stackoverflow.com/questions/35992900/bootstrap-accordion-scroll-to-top-of-active-open-accordion-on-click (Bootstrap 3 and 4)

- Bootstrap 3
<code>
$('.panel-collapse').on('show.bs.collapse', function(e) {
  var $panel = $(this).closest('.panel');
  var $open = $(this).closest('.panel-group').find('.panel-collapse.in');

  var additionalOffset = 0;
  if($panel.prevAll().filter($open.closest('.panel')).length !== 0)
  {
        additionalOffset =  $open.height();
  }
  $('html,body').animate({
    scrollTop: $panel.offset().top - additionalOffset
  }, 500);
});
</code>

- Bootsrap 3
<code>
$('.collapse').on('show.bs.collapse', function(e) {
  var $card = $(this).closest('.card');
  var $open = $($(this).data('parent')).find('.collapse.show');

  var additionalOffset = 0;
  if($card.prevAll().filter($open.closest('.card')).length !== 0)
  {
        additionalOffset =  $open.height();
  }
  $('html,body').animate({
    scrollTop: $card.offset().top - additionalOffset
  }, 500);
});
</code>

https://www.geeksforgeeks.org/how-to-accordion-scroll-to-top-to-open-content-in-bootstrap/ (Bootstrap 4)
