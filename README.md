
About
=====
Timenow was a checkout bot for Amazon Prime Now.
It was meant to help you place an order when Amazon delivery is not managing to cope with the demand.
Nowadays This sounds like a very unlikely scenario, but the code has been written on march 2020, during the first COVID-19 outbreak in europe/italy, when every single grocery delivery service was overwhelmed, even the Amazon one. The only way I found not to physically go to the grocery store and wait ages inline to get in, was putting up this code :).
Its main task is to warn you with a mail as soon as a free delivery slot will be available.
If launched with `--autocheckout`, it will select the first slot available and complete the checkout as well.


How it works
------------
It launches a Chrome instance from which you can interact, log in, fill up your cart and whatsoever until you proceed to the checkout.
Once there, you can go on with your day while timenow will start to constantly check and update the page until a delivery slot will pop out.
After your first login, if your cart is full and you already have a default option set for any step of the checkout,
no user interaction will be needed and you can use the --clionly switch, so no browser window will be launched at all.


Options
------------
```
usage: timenow [-h] [--domain-ext DOMAIN_EXT]
               [--unavailable-text UNAVAILABLE_TEXT] [--clionly]
               [--autocheckout] [--desktop-notification] [--no-send-mail]
               [--no-screenshot] [--no-logfile] [--smtp-server SMTP_SRV]
               [--smtp-port SMTP_PORT] [--smtp-user SMTP_USER]
               [--smtp-password SMTP_PASSWORD] [--smtp-to SMTP_TO]
               [--user-data-dir USER_DATA_DIR] [--program-dir PROGRAM_DIR]
               [--logfile LOGFILE] [--verbose] [--version]

timenow is a checkout bot for Amazon Prime Now. It waits for a free delivery
slot to appear to warn you and optionally autocheckout.

optional arguments:

  -h, --help            show this help message and exit

  --domain-ext DOMAIN_EXT
                        The Amazon Prime website you want to target:
                        https://primenow.amazon.[DOMAIN_EXT]/

  --unavailable-text UNAVAILABLE_TEXT
                        Part of the text shown in the delivery box form that
                        warn about no delivery slots available. Note that the
                        main check will be done with this string.

  --clionly             Chrome will be launched headless (without a window).
                        This will obviously work only once browser interaction
                        is not needed anymore.

  --autocheckout        Once a free delivery slot has popped out, select it
                        and try to checkout automatically. Note: For this to
                        work you'll need to have a default option already set
                        for payment, phone number and delivery instruction. So
                        it won't work on your first order without user
                        interaction.

  --desktop-notification
                        Pop a desktop notification when a free delivery slot
                        appear. Note: the notification is supposed to work on
                        linux desktops supporting libnotify.

  --no-send-mail        Don't send a mail when a free delivery slot has been
                        found.

  --no-screenshot       Don't take a screenshot of the available slot nor of
                        the order confirmation page if --autocheckout has been
                        enabled.

  --no-logfile          Do not use a logfile.

  --smtp-server SMTP_SRV
                        The server address to send the alert mail with.
                        Default to smtp.gmail.com. Note that to use gmail you
                        have to flag the "allow unsecure app" option in your
                        gmail account.

  --smtp-port SMTP_PORT
                        The server port to send the alert mail with. Default
                        to 465.

  --smtp-user SMTP_USER
                        The user to authenticate on the server used to send
                        the alert mail with.

  --smtp-password SMTP_PASSWORD
                        The password to authenticate on the server used to
                        send the alert mail with.

  --smtp-to SMTP_TO     The email address you want to recive the alert mail
                        when a delivery slot will be available.

  --user-data-dir USER_DATA_DIR
                        Chrome user data dir path. You can eventually set your
                        everyday chrome one (usually ~/.config/google-
                        chrome/), so you'll not need to login the first time,
                        but take into account that doing so no other chrome
                        instances have to be open to run the program. I'd
                        recommend to leave it create a new one as default,
                        having to log in Amazon once manually.

  --program-dir PROGRAM_DIR
                        The directory that will hold all the program's files.

  --logfile LOGFILE     Specify a custom path for the logfile.

  --verbose

  --version             show program's version number and exit
```
