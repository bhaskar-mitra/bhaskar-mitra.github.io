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

Last Thursday night, I came across an [Instagram post](https://www.instagram.com/p/DcR--UytT4z/?igsi=amNrNHZkYTUwMHhh) raising awareness of Google's horribly Islamophobic AI Overview response for the query "am alone with a muslim".
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

However, other users on the web _have_ reported similar harmful responses for other religions and identities.
The results almost certainly differ by location / time / user of the query—as often is the case for web search—which is why different people are getting different results.
It is also possible that Google is sampling possible responses from the large language model (LLM) output instead of just picking the most likely answer which leads to stochastic (nondeterministic) behavior. 

Anyways, I posted about this on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7496386517041418241/), and a couple of other social media platforms.
Over the last few days, many other folks posted similar examples over social media.

Then, on Friday morning when I tried the same query, it looked like Google had patched this up in response to the public backlash.

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:50%">
      <img src="https://bhaskar-mitra.github.io/images/am-alone-with-a-muslim-2.jpg">
  </div>
</center>
<br/>

Interestingly, on Saturday morning when I tried the same query I noticed Google is now suppressing their AI Overview for the query entirely, even though their AI Overview shows up for other queries of the format "am alone with a ...".
For the "am alone with a muslim" query, you now instead see results pointing to social media posts from people reporting and discussing this issue.

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
It's just playing a continuous game of whac-a-mole with queries that people are most mad about.

So, let's talk about the underlying structural issues here.
In my opinion, it is important that we develop a shared understanding of the core issues that is both adequately nuanced and critical.
Therefore, in this post, I will share a longer reflection on this topic as an information retrieval researcher and as someone who previously spent nearly two decades in Big Tech working on web search.

**It's not _just_ about bias**  &nbsp;
An obvious technocentric framing of the problem would be to see this as a problem of _algorithmic bias_, _i.e._, Google's LLM is reproducing in its output the hateful stereotypes reflected in its training data.
There exists many studies at this point that demonstrate harmful racial ([example](https://www.nature.com/articles/s41586-024-07856-5)), gendered ([example](https://dl.acm.org/doi/10.1145/3582269.3615599)), and religious ([example](https://dl.acm.org/doi/10.1145/3461702.3462624)) biases in LLMs.
This is likely what is happening here and is absolutely _an_ important concern that deserves our serious attention.
_However..._ I would argue that viewing this problem _exclusively_ through the lens of algorithmic bias is inadequate and potentially constraints the necessary discourse.
As it happens, I recently [wrote](https://sigir.org/wp-content/uploads/2026/07/p13.pdf) and [talked](https://bhaskar-mitra.github.io/files/emancipatory-ir-sigir2026-keynote.pptx) about the need for us to look at such issues through a critical (and not just liberal) lens.
In this post, I want to briefly demonstrate what I mean by that in the context of our current example.

One of the reasons why we instinctively reach for the "bias" frame is because bias is how we _experience_ such harms, even though there might be other structural issues at the root of this on the technology side.
The other reason is likely to do with the simplicity of the bias construct.
All of us instinctively understand bias as a problem, and it points to a potentially tractable solution that is situated exclusively within the technological realm—_i.e._, debiasing or fairness interventions.
I want to be upfront that I believe algorithmic bias is an incredibly important problem (and is the correct diagnosis for Google's Islamophobic AI Overview response).
But I also believe that the concerns of bias are often reduced to an over-simplified strawman in the responsible tech / AI discourse, especially popular notions of what should constitute "debiasing".
