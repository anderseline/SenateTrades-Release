# Welcome to SenateTrades!

[Newsletter Signup Form](https://docs.google.com/forms/d/e/1FAIpQLScnSVtK0tDMzJJEuNwqXYTuMK2RWexg0pDT3X9ZJiQHW6beeQ/viewform?usp=sf_link)

<i>This is the public repository for the now-private SenateTrades project</i>

<p>
    The goal of this program is to find small, under the radar companies whose equity has recently been disclosed as being purchased by US senators.
</p>

This project tracks market trading activity of US senators by publishing trades which are over a certain value, or involve a small company. The script scrapes the [SEC EDGAR Insider Trading Disclosures List](https://sec.report/Senate-Stock-Disclosures) and searches for trades which have been filed on the current day. Alerts are send over email and [twitter](https://twitter.com/Senate_Trades). In short, the logic for alerting a trade is:
- If the company is small (market cap under $2B), send an alert
- If the company is medium sized (market cap between $2B and $10B), and the value of the trade is over $50,000, send an alert
- If the trade is valued at over $100,000 regardless of company size, send an alert

This logic stems from the thought that senators buying small-sized companies seems a bit odd. Usually inidividuals with the amount of money and influence most senators have tend
to be very risk averse, investing little into stocks: and when they do, its usually in funds or very large, blue-chip companies. Buying small, volatile companies isn't something you'd expect to see from these kinds of people, which is why the program is more sensitive to sending out alerts if these kinds of stocks are purchased.

All trading history which the progam has sent alerts about can be found in this [informational dashboard](https://docs.google.com/spreadsheets/d/14eg98rZU5Rza-MeUQMQJAaJD90Iz4OwTniB5Pd4vrzE).

In addition, I also feed the equity information to [News API Client](https://newsapi.org/docs/client-libraries/python), retrieve the top recent/relevant articles, and include these in the email alert. The ticker in the body header also contains a link to the equity's [Yahoo Finance](https://finance.yahoo.com/) description page. There is also a link which leads to the senator's website containing their contact information. Here's an example of an alert email:

![](/res/repo_pics/sample_email.png)

And a tweet:

![](/res/repo_pics/sample_tweet.png)

The program is run multiple times a day to keep users updated on any potential trades that may be worth researching more. Historically, it tends to go off about once or twice a month. I made this as a side project while studying at Lehigh University, and I hope you find it interesting!

<b> If you have any other questions, please email:
ders.mailbot@gmail.com

Or, follow along on [twitter](https://twitter.com/Senate_Trades)
</b>

Credit to Jie Jenn for his Gmail and Google Sheets API scripts, especially his [Google.py](/main/Google.py) file.

![](/res/repo_pics/git_logo.JPG)
