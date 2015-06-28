MoneyCollector
==============
Simple website to accept payments through Stripe. You've gotta get a [Stripe account](https://stripe.com/).

You can see it action at [http://pay.longren.org/](http://pay.longren.org/). If you find this useful, feel free to drop me a few dollars for coffee and beer. :)

This was inspired by [begriffs/lucre, like this but in Ruby](https://github.com/begriffs/lucre).

If you find any issues or problems please report them using [the Issues tracker here at Github](https://github.com/tlongren/MoneyCollector/issues).

Ribbon CSS from [Josh Bader](http://codepen.io/joshbader/pen/ukFLi) and form CSS from [Joey](http://codepen.io/joe/pen/yGcnH).


Setup
-----------------------------
1. Open index.php and pay.php.

2. In index.php, change the __$yourName__ variable at line 2 to whatever you want it to be.

3. In Index.php, edit javascript variables __publicTestKey__ and __publicLiveKey__. You can find those keys in your Stripe settings. These keys are publishable.

4. In pay.php, set your private live key and your private test key (on line 12 and 13).

5. Upload all files to a PHP enabled webserver.

6. If you uploaded to a folder called pay-me at domain.com, your payment form will be at http://domain.com/pay-me/.

7a. To go live, open pay.php and replace __$privateTestKey__ with __$privateLiveKey__ inside the __Stripe::setApiKey__ method.

7b. Open index.php and replace __publicTestKey__ with __publicLiveKey__ inside the __Stripe.setPublishableKey__ javascript function.

8. For SSL, get a free SSL self-signed certificate from [tinycert.org](https://tinycert.org) and use [cloudflare](https://cloudflare.com) (pro account needed) or [Cloudbric](https://cloudbric.com).


Customization
-----------------------------
If you don't like the background image, it's really easy to change. There's some additional backgrounds in the assets folder, all are png files except the default. To change the background image, find the background you want in the assets folder, and copy the filename. Open style.css and replace __default_background.jpg__ on line 15 with the filename you copied from the assets folder. So, if you're switching to __black_lozenge.png__, you'd replace __default_background.jpg__ with __black_lozenge.png__. You'll also want to remove the __background-size__ property, and remove the __no-repeat center center fixed__ piece from line 15, otherwise your new background won't tile like it should.


So, basically, change this:
```CSS
body {
    background:url("/assets/default_background.jpg") no-repeat center center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
}
```

to this:
```CSS
body {
	background:url("/assets/black_lozenge.png");
}
```
