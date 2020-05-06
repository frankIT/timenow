
About
=====
Timenow is a checkout bot for Amazon Prime Now.
It is meant to help you place an order when Amazon delivery is not managing to cope with the demand.
Its main task is to warn you with a mail as soon as a free delivery slot will be available.
If launched with --autocheckout, it will select the first slot available and complete the checkout as well.


How it works
------------
It launches a Chrome instance from which you can interact, log in, fill up your cart and whatsoever until you proceed to the checkout.
Once there, you can go on with your day while timenow will start to constantly check and update the page until a delivery slot will pop out.
After your first login, if your cart is full and you already have a default option set for any step of the checkout,
no user interaction will be needed and you can use the --clionly switch, so no browser window will be launched at all.
