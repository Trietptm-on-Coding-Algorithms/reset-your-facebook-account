
# reset-your-facebook-account

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Version](https://img.shields.io/npm/v/reset-your-facebook-account.svg)](https://www.npmjs.com/package/reset-your-facebook-account) [![Downloads](https://img.shields.io/npm/dt/reset-your-facebook-account.svg)](https://www.npmjs.com/package/reset-your-facebook-account)

> Sometimes you want to start your Facebook activity again. So, here are some useful scripts to delete your Facebook posts, comments and likes.

## Prerequisites

Install [this Chrome extension](https://chrome.google.com/webstore/detail/jquery-injector/indebdooekgjhkncmgbkeopjebofdoid?hl=en) to include jQuery on the page.


Replace `your-facebook-username` in URLs with your Facebook username. Then start hacking. :smile:

## Likes
> https://www.facebook.com/your-facebook-username/allactivity?privacy_source=activity_log&log_filter=likes

```js
$("html, body").animate({ scrollTop: $(document).height() }, "slow");
setInterval(function () {
  var last = $("._6a._6b.uiPopover.rfloat a span").last().click();
  $("span:contains(Unlike):visible").click();
  var post = last.closest(".pam");
  post.prev().remove();
  post.remove();
}, 700);
```
## Posts
> https://www.facebook.com/your-facebook-username/allactivity?privacy_source=activity_log&log_filter=cluster_11

```js
$("html, body").animate({ scrollTop: $(document).height() }, "slow");
setInterval (function () {
  var last = $("._6a._6b.uiPopover.rfloat a span").last().click();
  $("span:contains(Delete):visible").click();
  setTimeout(function () {
    $("button:contains(Delete Post):visible").click();
    last.closest("table").remove();
  }, 1000);
}, 7000);
```
## Comments
> https://www.facebook.com/your-facebook-username/allactivity?privacy_source=activity_log&log_filter=cluster_116

```js
$("html, body").animate({ scrollTop: $(document).height() }, "slow");
setInterval (function () {
  var last = $("._6a._6b.uiPopover.rfloat a span").last().click();
  $("span:contains(Delete):visible").click();
  var post = last.closest("[data-ft]");
  post.prev().remove();
  post.remove();
}, 400);
```

If you find a bug, have a question or want a feature to be added, open [an issue](https://github.com/IonicaBizau/reset-your-facebook-account/issues).

## Delete messages
```js
var i = setInterval(function () {
  $ul = $("#wmMasterViewThreadlist")
  if (!$ul.find("li").length) return clearInterval(i);
  $ul.find("li").last().find("span").click()
  $("button:contains('Actions')").click()
  $("span:contains('Delete Conversation...')").click()
  $("input[value='Delete Conversation']").click()
}, 500);
```
## Clear timeline
> https://www.facebook.com/your-facebook-username/allactivity?privacy_source=activity_log&log_filter=all

```js
setInterval (function () {
  $("html, body").animate({ scrollTop: $(document).height() }, "slow");
  $('*[aria-label="Hidden from Timeline"]').each(function () {
    $(this).parents('.bottomborder').remove();
  });
  var allowed = $('*[aria-label="Allowed on Timeline"] span').last();
  allowed.click();
  $('.uiContextualLayer').find('li:nth-child(2)').find('a span').click();
  allowed.parents('.bottomborder').remove();
}, 400);
```

## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:



## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2014#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
