# Cookie_ConsentR
Add a Cookie consent banner to any website

This is a simple, customizable script that can help add a cookie banner to your website. It works both on mobile and desktop devices.

![Screenshot of Cookie_ConsentR](https://raw.githubusercontent.com/peteee/Cookie_ConsentR/master/img/Screen%20Shot%202018-05-23%20at%2017.12.02.png)



# 1. jQuery
Make sure your site uses jQuery (works with any version 1.x - 3.x). Otherwise import it first.

[jQuery from Google's CDN](https://developers.google.com/speed/libraries/#jquery)

1 3.x snippet:

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
2 2.x snippet:

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
3 1.x snippet:

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>


# 2. Paste it anywhere
within the <body> </body> tags

    <script type="text/javascript">
    jQuery(document).ready(function() {
      // Customize your texts here:
      var cCText = "We use cookies to give you the best experience on our website. If you continue without changing your settings, we will assume that you are happy to receive all cookies on this website.",
        cCBtnText = "OK",
        cCBtnText2 = "Privacy Policy",
        cCLink = "/privacy-policy/";
      // Style overides to change colors. Leave blank for default:
      var cCBGColor = "#4e4e4e",
        cCTextColor = "#fff",
        cCBtn1Color = "green",
        cCBtn1TextColor = "#eee",
        cCBtn2Color = "#da7614",
        cCBtn2TextColor = "#eee";
      /**
       * Stop editing ################################################/
       */
      window.COOKIE={create:function(e,t,n){if(n){var r=new Date;r.setTime(r.getTime()+24*n*60*60*1e3);var i="; expires="+r.toGMTString()}else i="";document.cookie=e+"="+t+i+"; path=/"},read:function(e){for(var t=e+"=",n=document.cookie.split(";"),r=0;r<n.length;r++){for(var i=n[r];" "==i.charAt(0);)i=i.substring(1,i.length);if(0==i.indexOf(t))return i.substring(t.length,i.length)}},erase:function(e){COOKIE.create(e,"",-1)}}
      window.COOKIE.read("CConsentR")||(jQuery("head").append("<style>#cookie-consentr{position:fixed;bottom:0;left:0;width:100%;text-align:center;background:#4e4e4e;color:#fff;padding:10px 0;font-size:14px;z-index:9999}#cookie-consentr p, #cookie-consentr p a{color:#fff}.c-c-btn{padding:3px 10px;border-radius:10px;cursor:pointer;display:inline-block;}.c-c-btn:hover{opacity: 0.8}#c-c-ok{background:green}#c-c-link{background:green}</style>"),jQuery("body").append('<div id="cookie-consentr" style="background:'+cCBGColor+'"><p style="color:'+cCTextColor+'">'+cCText+' <a class="c-c-btn" id="c-c-ok" style="background:'+cCBtn1Color+";color:"+cCBtn1TextColor+'">'+cCBtnText+'</a> <a href="'+cCLink+'" target="_blank" class="c-c-btn" id="c-c-link" style="background:'+cCBtn2Color+";color:"+cCBtn2TextColor+'">'+cCBtnText2+"</a></p></div>"),jQuery("#c-c-ok").bind("click",function(o){o.stopPropagation(),o.preventDefault(),window.COOKIE.create("CConsentR",!0,1095),jQuery("#cookie-consentr").remove()}))
    });
    </script>




# Erase Cookie
Want to see it again?
just call from your browser console or script:

    COOKIE.erase('CConsentR');

## Features
- colors/CSS can be styled
- texts can be adjusted
- link to your own Privacy Policy / Cookie Policy can be added easily
- cookie expires after 3 years

## Todo
- external JS
- make minified version
- make cookie expiration adjustable (default = 3yrs)

## Caution
This script uses cookies, LOL! Works on both desktop and mobile devices.

## Disclaimer
This script does not guarantee GDPR/DSGVO, PECR/ePrivacy or any other compliance. Use at your own risk!
In no event shall the author be liable for any special, direct, indirect, consequential,
or incidental damages or any damages whatsoever, whether in an action of contract,
negligence or other sort, arising out of or in connection with the use of the script or the contents of the script.

## Need help, or customization?
Drop me a line: pete at wayoutofline dot net
