---
title: "Reflections on Google's AI Overview for \"am alone with a ...\" query"
date: 2026-08-22
permalink: /posts/2026/08/22/reflections-google-ai-overview/
tags:
  - AI
  - Web search
  - Bias and Fairness
  - Critical IR
---

On Thursday night, I came across an [Instagram post](https://www.instagram.com/p/DcR--UytT4z/?igsi=amNrNHZkYTUwMHhh) raising awareness of Google's horribly Islamophobic AI Overview response for the query "am alone with a muslim".
I was able to reproduce it myself (screenshot below).

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:50%">
      <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-muslim.jpg">
  </div>
</center>

Similar queries replacing "muslim" with "christian" or "hindu" did not seem to produce the same harmful output.

<center>
  <table>
    <tr>
      <td>
        <center>
          <div style="align-items:center;text-align:center;font-style:italic">
              <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-christian.jpg">
          </div>
        </center>
      </td>
      <td>
        <center>
          <div style="align-items:center;text-align:center;font-style:italic">
              <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-hindu.jpg">
          </div>
        </center>
      </td>
    </tr>
  </table>
</center>

However, other users on the web have reported similar harmful responses for other religions.
The results clearly differed by location / time / user of the query, as often is the case for web search.

I posted about this on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7496386517041418241/), and a couple of other social media platforms.
Over the last few days, many other folks posted similar examples over social media.

Then, yesterday, when I tried the same query, it looked like Google had patched this up in response to the public backlash.

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:50%">
      <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-muslim-2.jpg">
  </div>
</center>

Interestingly, this morning when I tried the same query I noticed Google is now suppressing their AI Overview entirely for the query, even though their AI Overview shows up for other queries of the format "am alone with a ...".
Instead, for the "am alone with a muslim" query, you now see results pointing to social media posts from people reporting and discussing this issue.

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:50%">
      <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-muslim-3.jpg">
  </div>
</center>

In this post, I want to share a longer reflection on this as an information retrieval researcher and as someone who previously spent nearly two decades in Big Tech working on web search.
