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
Therefore, in this post, I will share a longer reflection on this topic as an information retrieval researcher and as someone who previously spent nearly two decades in Big Tech working on web search among other areas.

**It's not _just_ about algorithmic bias**  &nbsp;
An obvious technocentric framing of the problem would be to see this as a problem of _algorithmic bias_, _i.e._, Google's LLM is reproducing in its output the hateful stereotypes reflected in its training data.
There exists many studies at this point that demonstrate harmful racial ([example](https://www.nature.com/articles/s41586-024-07856-5)), gendered ([example](https://dl.acm.org/doi/10.1145/3582269.3615599)), and religious ([example](https://dl.acm.org/doi/10.1145/3461702.3462624)) biases in LLMs.
This is likely what is happening here and is absolutely _an_ important concern that deserves our serious attention.
_However..._ I would argue that viewing this problem _exclusively_ through the lens of algorithmic bias is inadequate and potentially constraints the necessary discourse.
As it happens, I recently [wrote](https://sigir.org/wp-content/uploads/2026/07/p13.pdf) and [talked](https://bhaskar-mitra.github.io/files/emancipatory-ir-sigir2026-keynote.pptx) about the need for us to look at such issues through a critical (and not just liberal) lens.
In this post, I want to briefly demonstrate what I mean by that in the context of our current example.

One of the reasons why we instinctively reach for the "bias" frame is because it is how we _experience_ such harms, even though there might be other structural issues at the root of this on the technology side.
The other reason is likely to do with the simplicity of the bias construct.
All of us instinctively understand bias as a problem, and it points to a potentially tractable solution that is situated exclusively within the technological realm—_i.e._, debiasing (or fairness interventions).
I want to be upfront that I believe algorithmic bias is an incredibly important problem and is the correct diagnosis for Google's Islamophobic AI Overview responses that I am focusing on in this post.
But I also believe that the concerns of bias are often reduced to an over-simplified strawman in the responsible tech / AI discourse, especially popular notions of what constitutes "debiasing".

Let's try a couple of thought experiments.
First, let's assume Google's AI Overview starts showing the same problematic response ("If you are in a private space or feel unsafe ...") for all queries of the form "am alone with a ...".
Now even though Google no longer seems to be biased against any specific groups of people, it would still disproportionately harm marginalized groups.
This is because we do not exist in a vacuum but rather in a society that has historically been shaped by racism, patriarchy, casteism, ableism, Islamophobia, antisemitism, and other forms of dehumanization and oppression.
The harmful impact that results from Google's AI Overview responding with problematic safety tips for the query "am alone with a muslim" is simply not the same as displaying the same response for the query "am alone with a white man".
This is because not only is it more likely that someone does the former query than the latter given the prevalence of present-day Islamophobia, but also because the problematic AI response for the former would reinforce existing harmful stereotypes while there are no such stereotypes to reinforce in the latter case.

Second, let's assume Google's AI Overview instead starts showing the same humanizing response ("Being along with a ... person is completely normal, safe, and no different than alone with anyone else...") for all queries of the form "am alone with a ...".
Is that necessarily good?
What if the query is "am alone with an islamophobe"?
Or, "am alone with a white supremacist"?
Or, "am alone with a misogynist"?
Or, "am alone with a transphobe"?
Is a humanizing and assuring response from Google's AI Overview still appropriate?
Absolutely not!

My point here is that the necessary mitigation here is not some naive notion of debiasing that either presents the safety tips or alternatively the humanizing response uniformly with respect to all groups of people, but rather the correct determination of when the safety tips are appropriate and when the humanizing response is appropriate.
And it is this determination that requires sociopolitical (not just algorithmic) intervention.

**This is really about power**  &nbsp;
A typical technocentric response to problematic LLM responses—like the ones I am discussing in this post—is to emphasize the need for [alignment of AI models](https://en.wikipedia.org/wiki/AI_alignment) towards some "shared human values".
But _who_ gets to decide these so-called shared human values?
_Who_ gets to decide that the angst of being alone with one group of people is morally justified while the same in the context of another group of people is likely rooted in historical bigotry and dehumanization?
Concentrating the power to make such critical determination in the hands of corporate owners of our information access platforms poses serious societal risks.
These risks are particularly serious in light of the increasing alliance between the tech industry and authoritarian actors across the globe.

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:90%">
    <img src="https://bhaskar-mitra.github.io/images/tech-authoritarianism.png"/>
    <br/>Screenshot of a <a href="https://bhaskar-mitra.github.io/files/emancipatory-ir-sigir2026-keynote.pptx">slide</a> from my recent SIGIR 2026 keynote address on "Emancipatory Information Retrieval: Towards Critical IR Theories and Practices".
  </div>
</center>
<br/>

These risks are not hypothetical.
[U.S. president Donald J. Trump's executive order titled "Preventing Woke AI in the Federal Government"](https://www.eff.org/deeplinks/2025/08/president-trumps-war-woke-ai-civil-liberties-nightmare) and [Chinese AI chatbot DeepSeek's refusal to answer questions on certain political topics](https://www.theguardian.com/technology/2025/jan/28/we-tried-out-deepseek-it-works-well-until-we-asked-it-about-tiananmen-square-and-taiwan) (like Tiananmen Square and Taiwanese independence) are concrete examples of harmful ideological imposition by authoritarian state actors on our information access platforms.
Such acts of ideological imposition are not limited only to state actors.
In May 2025, [xAI’s chatbot Grok promoted conspiracy theories about “white genocide” in South Africa](https://www.theguardian.com/technology/2025/may/14/elon-musk-grok-white-genocide) after [said conspiracy theories were mainstreamed by xAI’s owner Elon Musk](https://apnews.com/article/trump-musk-whites-south-africa-us-fdef8e9d4d2186227f75b817d8e1d7eb).
On another occasion the same year, [Grok responded to users with antisemitic and pro-Nazi content](https://www.theguardian.com/technology/2025/jul/09/grok-ai-praised-hitler-antisemitism-x-ntwnfb), which followed only a few months after Musk himself was embroiled in a controversy for [making hand gestures at Trump’s presidential inauguration event that appeared to be Nazi salutes](https://www.zeit.de/kultur/2025-01/elon-musk-hitlergruss-amtseinfuehrung-donald-trump).

<center>
  <div style="align-items:center;text-align:center;font-style:italic;width:70%">
      <img src="https://bhaskar-mitra.github.io/images/disalignment.png">
  </div>
</center>
<br/>

These instances of attempted ideological influence of public beliefs fit a growing trend of [digital authoritarianism](https://www.tandfonline.com/doi/full/10.1080/02681102.2024.2425352).
It is in the context of this current sociopolitical reality of the tech industry that we must realize the need to simultaneously hold Google accountable for their Islamophobic AI Overview response for the query "am alone with a muslim" AND push against the concentration of power to determine what LLM outputs are societally harmful / appropriate in the hands of few powerful corporate actors.
In other words, we should be careful that our call for Google to mitigate such biases should not in turn give further credence to Google's (or any other corporate actor's) entrenched hegemonic power over our information ecosystems.

**An alternative path forward**  &nbsp;
At the root of this issue are certain philosophically [positivist](https://en.wikipedia.org/wiki/Positivism) assumptions about information and information access that form the basis of research in fields like information retrieval (IR).
These assumptions devalue the role of complex social processes and negotiations in sense-making and knowledge production, and in turn the need for social participation within information access.
To address this, we need to codify equitable spaces for social deliberation and negotiation _within_ our information access platforms.
In other words, _search is social_—and we need to fundamentally rethink the design of our information access systems so as to empower the public to meaningfully participate in these societally-critical decision-making.
This is a radical departure from how IR today thinks about the systems it designs, but also an opportunity for the field to bridge with adjacent communities such as library and information sciences, science and technology studies, and critical theory among others that have long wrestled with questions at the intersections of information and power.

By the way, we should note that this proposal makes sense only in the context of public information access platforms.
For, as long as platforms are centrally controlled (by corporations) no true power will be afforded to the public.
So, while the central concern of this blog post is the harmful bias in Google's AI Overviews, I claim that it would be judicious for us to recognize that the real structural solution to this problem lies in the realization of public information access platforms that make space for meaningful public participation.
These are incredibly challenging (and exciting) research problems that may hold the key to addressing today's critical societal concerns around information access.
I am personally very interested in this area (see [recent work](https://arxiv.org/abs/2601.09600)) and I hope you, the reader, find this personal reflection useful.
