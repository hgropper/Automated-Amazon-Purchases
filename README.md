# Automated-Amazon-Purchases
At the start of the coronavirus, many people were scrambling to gather computer parts. As a result, GPU (Graphics Processing Units) prices skyrocketed. This high demand leads to high prices, and people buy them like crazy. Note that these GPUs went out of stock right away... within seconds! Could I make a bot to buy one for myself? - Yes, I can.

## Problems:
- Amazon's anti-bot security: Amazon is pretty clever in dealing with bots navigating their website, but there are some work arounds. 
Faking the user-agent and cookies allowed me to navigate the website with my program. 
- IP blocks: This was easily solved my implementing an automatic VPN switcher in my program when needed.

### VPN Rotater
Amazon doesn't like when people bombard their servers with multiple requests. Especially when hundreds of requests are coming from one person or internet address, my IP address would frequently become blocked, and I would not be able to make requests. Solution: rotate my IP address with [NordVPN](https://nordvpn.com/cybersecurity-site/), when needed. To do this in my program I used a module someone else created called [NordVPN Switcher](https://pypi.org/project/nordvpn-switcher/).
- It was extremely important to NOT rotate your VPN when logged into your Amazon account
- This is a huge red flag to Amazon and they would instantly notice your suspicious activity

## How does my program work?
- I would have have multiple ASIN codes scanned by my program 24/7 (Amazon Standard Identification Number) of products I was interested in buying.
- Once my program detected that an item was in stock, it would then transition to the buying phase
- In this phase, my program would disconnect from the VPN 
- Login to Amazon with my account information
- Purchase the item I wanted as fast as the program could
- If the purchase was successful, then send a text message and end the program OTHERWISE go back to the top (step 1)
- After the purchase I used [Twilio's](https://www.twilio.com/) service to notify me of the successful purchase
- program ends
