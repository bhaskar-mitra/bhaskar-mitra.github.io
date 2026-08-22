---
title: "Reflections on Google's AI Overview for \"am alone with a muslim\" query"
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
<br/>

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
<br/>

Interestingly, this morning when I tried the same query I noticed Google is now suppressing their AI Overview entirely for the query, even though their AI Overview shows up for other queries of the format "am alone with a ...".
Instead, for the "am alone with a muslim" query, you now see results pointing to social media posts from people reporting and discussing this issue.

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:50%">
      <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-muslim-3.jpg">
  </div>
</center>
<br/>

The patch up and the subsequent suppression of AI Overview for this query is unsurprising.
Systemic fixes for such problems are hard.
So, tech companies typically rush out a band-aid fix by editorially changing the results for highly visible cases that are garnering immediate public backlash.
Remember the [infamous example](https://www.bbc.com/news/newsbeat-32332603) of Google's image search results for the query "CEO" predominantly showing photos of white men?
I wouldn't be surprised if a decade later Google/Bing's results for that query are still being highly editorialized.
Editorially fixing LLM outputs are harder, so suppressing AI Overview results for the query becomes the next logical "solution".
However, obviously neither of these interventions addresses the underlying systemic problem that this example surfaces.

So, let's talk about the underlying structural issue here.
In my opinion, this needs to be a nuanced conversation for us to collectively make real sense of the situation.
Towards that goal, in this post, I will share a longer reflection on this topic as an information retrieval researcher and as someone who previously spent nearly two decades in Big Tech working on web search.

**It's not _just_ about bias**  &nbsp;
An obvious technocentric framing of the problem would be through the lens of _bias and fairness_, i.e., Google's LLM is reproducing in its output the hateful stereotypes reflected in its training data.
This is likely what is happening here and is absolutely _an_ important concern that deserves our serious attention.
_However..._ I would argue that viewing this problem _exclusively_ through a bias and fairness lens is inadequately narrow and potentially distracts us from a bigger critical discourse.
As it happens, I recently [wrote](https://sigir.org/wp-content/uploads/2026/07/p13.pdf) and [talked](https://bhaskar-mitra.github.io/files/emancipatory-ir-sigir2026-keynote.pptx) about the need for us to look at such issues through a critical (and not just liberal) lens.
In this post, I want to briefly demonstrate what I mean in the context of our current example.

While algorithmic bias is an incredibly important problem, I also believe that this framing is over-used in responsible tech / AI discourse.
Part of the reason is that 
