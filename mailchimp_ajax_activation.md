Markup
-----------
<div class="subscribe-widget clearfix">
    <h4>Subscribe to Our Newsletter</h4>
    <!-- ===== MAILCHIMP FORM STARTS ===== -->
    <form class="mailchimp inputSubscribeDiv">
        <!-- SUBSCRIPTION SUCCESSFUL OR ERROR MESSAGES -->
        <input type="email" name="subscribe" id="subscriber-email" placeholder="Enter your Email" class="form-control">
        <button type="submit" id="subscribe-button" class="btn btn-blue ">Subscribe</button>
        <h5 class="subscription-success"> </h5>
        <h5 class="subscription-error"> </h5>
        <label class="subscription-label" for="subscriber-email"></label>
    </form>
    <!-- /END MAILCHIMP FORM STARTS -->
</div>




jQuery activation
-----------------------

(function ($) {
"use strict"; 


 // mailchimp start
    if ($('.mailchimp').length > 0) {
        /*  MAILCHIMP  */
        $('.mailchimp').ajaxChimp({
            language: 'es',
            callback: mailchimpCallback,
            url: "https://themepure.us14.list-manage.com/subscribe/post?u=5b0af3eccc324cd420b6ae5e5&amp;id=2416850e34" //Replace this with your own mailchimp post URL. Don't remove the "". Just paste the url inside "".
        });
    }

    function mailchimpCallback(resp) {
        if (resp.result === 'success') {
            $('.subscription-success').html('<i class="fa fa-check"></i><br/>' + resp.msg).fadeIn(1000);
            $('.subscription-error').fadeOut(500);

        } else if (resp.result === 'error') {
            $('.subscription-error').html('<i class="fa fa-times"></i><br/>' + resp.msg).fadeIn(1000);
        }
    }
    $.ajaxChimp.translations.es = {
        'submit': 'Submitting...',
        0: 'We have sent you a confirmation email',
        1: 'Please enter a value',
        2: 'An email address must contain a single @',
        3: 'The domain portion of the email address is invalid (the portion after the @: )',
        4: 'The username portion of the email address is invalid (the portion before the @: )',
        5: 'This email address looks fake or invalid. Please enter a real email address'
    };

	
})(jQuery);	