# Automated-Amazon-Purchases
At the start of the coronavirus many people were scrambling to gather computer parts. As a result the prices of GPU's (Graphics Processing Units) sky rocketed. This high demand lead to high prices, and people buying them up like crazy. Note that these GPU's went out of stock right away... within seconds! Could I make a bot to buy one for myself? - Yes I can.

## Problems:
- Amazon's anti bot security: Amazon is pretty clever in how they deal with bots navigating their website, but there are some work arounds. 
I found that faking the user-agent and cookies allowed me to navigate the website with my program. 
- IP blocks: This was easily solved my implementng an automatic vpn switcher in my program when needed.

### VPN Rotater
Amazon doesn't like when people are bombarding their servers with mutliple requests. Especially when hundreds of requests are coming from one person or internet address. So, my IP address would frequently become blocked, and I would not be able to make requests. Solution: rotate my IP address with [NordVPN](https://nordvpn.com/cybersecurity-site/), when needed. To do this in my program I used a module someone else created called [NordVPN Switcher](https://pypi.org/project/nordvpn-switcher/).
- It was extremely important to NOT rotate your VPN when logged into your Amazon account
- This is a huge red flag to Amazon and they would instantly notice your suspicious activity

## How does my program work?
- I would have have multiple ASIN codes scanned by my program 24/7 (Amazon Standard Identification Number) of products I were interested in buying.
- Once my program detected that an item was in stock it would then transition to the buying phase
- In this phase my program would disconnect from the VPN and immediately purchase the item I wanted
- After the purchase I used [Twilio's](https://www.twilio.com/) service to notify me of the purchase
- program ends
