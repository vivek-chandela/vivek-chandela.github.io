---
layout: post
title:  "Market Returns"
date:   2021-07-18 19:03:00 +0530
category: PeFi
---
There are three primary ways of calculating market returns:

### 1. Absolute return

>Absolute return = (Selling price - Buying price)/Buying Price

This method works when selling and buying, both, happen once within the same year.

***Absolute return isn’t a viable measure of calculating returns from multi-year investments.***

***It does not help to calculate SIP returns.***
<br><br>

### 2. CAGR (Compound Annual Growth Rate)

Everyone knows the formula for Compound Interest: Selling Price = Buying Price(1+r)^n

CAGR is just the formula for compound interest where we bring everything to one side to find the rate of interest(r)

>CAGR = [ (Selling price/Buying price)^(1/n) - 1 ] where, n = time in years

CAGR is an upgrade on absolute return as it works for multi-year investments.

E.g., An agent asks you to invest a lump sum of 2 Cr today and promises you 8 Cr at the end of 25 years. Will you invest?

Here, Absolute return = (8-2)/2 = 300% !!!

Let's check the CAGR = (8/2)^(1/25) - 1 = 5.70 % which is quite low.

Hence, it isn’t advisable to use insurance as an investment instrument. Instead, we can take a term plan which comes at a meager price and invest the remaining amount elsewhere.

For CAGR, we are just concerned with the lump sum at the time of investment and withdrawal. We don't care what's the return each year. It automatically takes that into account. 
As a result, CAGR is vital for the selection of a mutual fund.

E.g.,

<p align="center">
<img src="/pefi/assets/images/cagr.png" alt="position" width="250" height="250"/>
</p>

Here, CAGR = (16000/10000)^(1/5) - 1 = 9.86%

***CAGR also doesn't work for SIP returns***
<br><br>

### 3. XIRR (Extended Internal Rate of Return)

Let’s say you make a monthly SIP of ₹ 10,000 for three years. So, you have invested in 36 installments, and at the end of 3 years, your portfolio value is ₹ 400000.

At the end of the 36 months, if you want to calculate your portfolio return, you will have to figure out CAGR for 35 months, 34 months, 33 months for different investments you made, and hence quite complicated.

XIRR makes this simpler by calculating one return for your investments.

E.g.,

<p align="center">
<img src="/pefi/assets/images/xirr.png" alt="position" width="250" height="400"/>
</p>

Note: -1000 means you invested 1000 rupees, and 14500 means you withdrew this amount

In the above example, absolute returns give a false impression of the returns.

>To conclude, while CAGR works great for lump sum investments, XIRR is the correct approach when dealing with a series of investments.

**References:** [link-1](https://www.youtube.com/watch?v=JLigdg8sR1A&t=648s) [link-2](https://www.youtube.com/watch?v=Azi4VQhlQFw&t=856s)

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>