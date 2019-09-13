# How to Read/Write cookies in Salesforce

What are Cookies ?

Cookies are small files which are stored on a user's computer. They are designed to hold some amount of data specific to a particular client and website, and can be accessed either by the web server or the client computer. In simple we can say that Its a small memory to store some information for some interval of time. Generally we use this to store user's preferences for a particular website.

Storing Content in Cookies in Salesforce:

In Salesforce we have Cookie class which is used to create Cookie.

 Cookie cookie = new Cookie('WPDEMO',enteredCookieData,null,-1,false);

In Cookies constructor we pass :

First Parameter : Cookie Key
Second Parameter : Cookie Key's Value
Third Parameter : Path
Fourth Parameter : Maximum Age
Fifth Parameter : isSecure

Once we create Cookie object we can set this cookie with Current Page so that anyone who access url with same domain can access the cookie.

ApexPages.currentPage().setCookies(new Cookie[]{cookie});

We set the created cookie on current page.




Reading Content in Cookies in Salesforce:

To read cookie we have to get all cookies on current page. And from that cookies map we can get our cookie by using the name we have used while creating cookie.

Cookie cookie = ApexPages.currentPage().getCookies().get('WPDEMO');

This will return Cookie object and from that object we can get value by getValue() method. This will return value of that cookie.

cookieValue = cookie.getValue();

To know more about, refer to my blog post @ http://blog.singhtarandeep.com/blog/2017/08/17/readwrite-cookies-salesforce/
