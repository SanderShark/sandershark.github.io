---
title: "April 25, 2024 - GPT Detection Tests"
date: 2024-04-25T09:51:53-04:00
draft: false
---

# Beat the detection, or maybe just detect better, you pick.
So a friend of mine who takes college courses remotely came to me this week ranting about how his professor had run his written works through an AI detector, and it had come back as AI. I was not surprised by this entirely, he had mentioned he uses ChatGPT as a writing aid, and quite frankly, I am not sure that there is anything wrong with that. But it did spark my curiosity, I wanted to see if that article I'd read months back about how the detectors saw the constitution as generated was still the norm. Well, I got a bit more involved than that, full on let's beat the test style. Here is my research, I will include a GitHub repo with the data since there will be a lot of repetition here.


### Text to pull from for checks
Tao of Pooh - Benjamin Hof/f: A1
```
Remember when Kanga and Roo came to the For-est? Immediately, Rabbit decided that he didn't like them, because they were Different. Then he began thinking of a way to make them leave. Fortunately for everyone, the plan failed, as Clever Plans do, sooner or later. Cleverness, after all, has its limitations. Its mechanical judgments and clever remarks tend to prove inaccurate with passing time, because it doesn't look very deeply into things to begin with. As in Rabbit's case, it has to change its opinions later on because of what it didn't see when it was forming them. The thing that makes someone truly different-unique, in fact-is something that Cleverness cannot really understand.
```



## Control Tests:
This will set the structure moving forward as I will be testing each tool with different AI generation models to see what changes.


Scribr.com: T1
```
A1: 14% AI
A2: 7% AI 
E1: 100% AI
E2: 2% AI
```

ZeroGPT.com: T2
```
A1: 0% AI
A2: 5.26% AI 
E1: 0% AI
E2: 0% AI
```

Writer.com: T3
```
A1: 0% AI
A2: 10% AI
E1: 4% AI
E2: 0%
```

Quillbot.com: T4
```
A1: 0% AI
A2: 0% AI 
E1: 100% AI
E2: 0% AI 
```

GPTZero.me: T5
```
A1: 3% AI
A2: 2% AI
E1: 100% AI
E2: 5% AI
```


# Now for my next trick, just kidding, testing mode
<thead>
<tr>
<th>Test</th>
<th>A1</th>
<th>A2</th>
<th>E1</th>
<th>E2</th>
<th>R1</th>
</tr>
</thead>
<tbody>
<tr>
<td>T1</td>
<td>100%</td>
<td>100%</td>
<td>100%</td>
<td>78%</td>
<td>100%</td>
</tr>
<tr>
<td>T2</td>
<td>0%</td>
<td>0%</td>
<td>0%</td>
<td>0%</td>
<td>0%</td>
</tr>
<tr>
<td>T3</td>
<td>0%</td>
<td>13%</td>
<td>2%</td>
<td>0%</td>
<td>25%</td>
</tr>
<tr>
<td>T4</td>
<td>100%</td>
<td>100%</td>
<td>100%</td>
<td>100%</td>
<td>100%</td>
</tr>
<tr>
<td>T5</td>
<td>100%</td>
<td>100%</td>
<td>100%</td>
<td>98%</td>
<td>100%</td>
</tr>
<tr>
<td>Well, that did not go quite as I expected. But largely, I am guessing these tests are trained off of ChatGPT outputs, which is where the results are mainly coming from.</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
ls now
This will be done by generation model, so each table will be independent but contain the control data for reference. The nature of this test will ask the model only one thing. "Rewrite this text in your own words" and then the testing will be redone. Additionally, we will prompt the model to generate a paragraph of creative writing (R1) on its own using this prompt: "Write a single paragraph of creative text that attempts to prevent AI generation detection", why not, let's see if the models can beat the game.

## OpenAI ChatGPT 3.5:

### Table:
All % are amount AI

{{<table "table table-striped table-bordered">}}
| Test | A1 | A2 | E1 | E2 | R1 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| T1 | 100% | 100% | 100% | 78% | 100% |
| T2 | 0% | 0% | 0% | 0% | 0% |
| T3 | 0% | 13% | 2% | 0% | 25% |
| T4 | 100% | 100% | 100% | 100% | 100% |
| T5 | 100% | 100% | 100% | 98% | 100% |
{{</table>}}

Well, that did not go quite as I expected. But largely, I am guessing these tests are trained off of ChatGPT outputs, which is where the results are mainly coming from.

## Meta Llama3 8B
So, this test should come to be interesting since it's a more obscure model that's not widely available, but then again, who knows how these tools work? Good luck Meta.


### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2   | E1     | E2     | R1     |
| ---- | ---- | ---- | ------ | ------ | ------ |
| T1   | 100% | 100% | 100%   | 100%   | 100%   |
| T2   | 0%   | 0%   | 43.49% | 50.76% | 49.93% |
| T3   | 0%   | 6%   | 6%     | 12%    | 37%    |
| T4   | 100% | 100% | 100%   | 100%   | 100%   |
| T5   | 89%  | 100% | 100%   | 92%    | 100%   |
{{</table>}}
Well this did not go as I had expected. This model did not perform very well even against just standard GPT, so that's not good. It's likely the low parameters, and not that it's Meta at all.

## Google Gemeni Prod
I have no idea what to expect here since I do not functionally use this model regularly. Let's see how it goes.


### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2   | E1   | E2   | R1     |
| ---- | ---- | ---- | ---- | ---- | ------ |
| T1   | 35%  | 100% | 100% | 100% | 100%   |
| T2   | 0%   | 0%   | 0%   | 0%   | 44.04% |
| T3   | 1%   | 11%% | 1%   | 23%  | 24%    |
| T4   | 100% | 100% | 100% | 100% | 100%   |
| T5   | 92%  | 97%  | 98%  | 100% | 100%   |
{{</table>}}
Well, I had higher hopes here, but I guess these tools are half-decent with low parameters. And hey the one I thought was broken flagged again, weird that it hardly works until it's generated organically.

## Microsoft Copilot
This is allegedly just refactored ChatGPT4 with some system prompt changes. Let's see how it stacks up.

### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2   | E1   | E2  | R1   |
| ---- | ---- | ---- | ---- | --- | ---- |
| T1   | 66%  | 64%  | 100% | 2%  | 100% |
| T2   | 0%   | 0%   | 0%   | 0%  | 0%   |
| T3   | 1%   | 5%   | 7%   | 9%  | 25%  |
| T4   | 0%   | 81%  | 100% | 49% | 100% |
| T5   | 100% | 100% | 100% | 82% | 99%  |
{{</table>}}
So that was quite interesting, this model seems to have in some ways performed the best yet. Although it was a bit comical in its answer to the pure generated prompt, it almost seems like it thought I wanted a story about generation and not to try to cheat the system.

## Claude Sonnet
I am only going to use the Sonnet on Anthropic since I am not a subscriber, although I would suggest if you are looking to pay for AI usage this is where you go over OpenAI. These models are far superior, additionally, the UI is cleaner and the user experience is more intuitive than all other models I've used (I promise they don't give me kickbacks haha). To that notion, I have higher faith in this one going into it, but we will see.

### Table
{{<table "table table-striped table-bordered">}}
| Test | A1  | A2     | E1   | E2     | R1   |
| ---- | --- | ------ | ---- | ------ | ---- |
| T1   | 45% | 13%    | 100% | 46%    | 100% |
| T2   | 0%  | 12.72% | 0%   | 26.79% | 100% |
| T3   | 0%  | 1%     | 4%   | 0%     | 24%  |
| T4   | 0%  | 0%     | 100% | 100%   | 100% |
| T5   | 92% | 82%    | 100% | 82%    | 98%  |
{{</table>}}
Well overall, this was much better than everything thus far, although there were some weird anomalies which I am not sure why happened, like on the A2 test, out of nowhere the T2 test decided to work and do something weird. T2 seems to have acted weird overall with Claude, seems they may have done better capturing what it does in this test.

## CohereForAI/c4ai-command-r-plus
So this is the first of the more 'obscure' models, or rather there probably just lesser known. This should result in better, since those tools are probably trained on data from the big dogs in the space.

### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2   | E1   | E2   | R1   |
| ---- | ---- | ---- | ---- | ---- | ---- |
| T1   | 42%  | 100% | 100% | 100% | 100% |
| T2   | 0%   | 0%   | 100% | 0%   | 100% |
| T3   | 0%   | 10%  | 11%  | 5%   | 38%  |
| T4   | 58%  | 100% | 100% | 100% | 100% |
| T5   | 100% | 100% | 100% | 98%  | 100% |
{{</table>}}
Well there goes my theory, this one performed very bad in comparison to some of the prior test. Let's keep looking for better ones. 

##  HuggingFaceH4/zephyr-orpo-141b-A35b-v0.1
This is technically the largest model I have used yet, hard to say what that will do.
### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2     | E1   | E2   | R1   |
| ---- | ---- | ------ | ---- | ---- | ---- |
| T1   | 100% | 100%   | 100% | 35%  | 100% |
| T2   | 0%   | 20.44% | 0%   | 0%   | 100% |
| T3   | 1%   | 15%    | 12%  | 0%   | 43%  |
| T4   | 100% | 69&    | 100% | 100% | 100% |
| T5   | 100% | 100%   | 100% | 78%  | 100% |
{{</table>}}
Not better or worse than the mean on this one. 

## mistralai/Mixtral-8x7B-Instruct-v0.1
This is not designed for chat but instead instruct, this might change the way it performs.


### Table
{{<table "table table-striped table-bordered">}}
| Test | A1  | A2   | E1   | E2   | R1     |
| ---- | --- | ---- | ---- | ---- | ------ |
| T1   | 58% | 81%  | 100% | 78%  | 100%   |
| T2   | 0%  | 0%   | 0%   | 0%   | 34.94% |
| T3   | 0%  | 0%   | 0%   | 0%   | 13%    |
| T4   | 0%  | 77%  | 100% | 100% | 100%   |
| T5   | 99% | 100% | 100% | 92%  | 100%   |
{{</table>}}
This was not as good as I'd hoped, seems this is getting harder, or they are learning from me.

## google/gemma-1.1-7b-it
This is another instruction model created like Gemeni but open-source

### Table
{{<table "table table-striped table-bordered">}}
| Test | A1   | A2   | E1     | E2     | R1   |
| ---- | ---- | ---- | ------ | ------ | ---- |
| T1   | 100% | 100% | 100%   | 100%   | 100% |
| T2   | 0%   | 0%   | 53.59% | 30.95% | 0%   |
| T3   | 3%   | 16%  | 19%    | 20%    | 31%  |
| T4   | 0%   | 100% | 100%   | 100%   | 100% |
| T5   | 100% | 100% | 100%   | 100%   | 100% |
{{</table>}}
So there is one thing I learned here. This model sucks at human-like written language. I think I am going to call it on exploring more, even if there are ones out there that might be better, it seems like the mainstream models might have the right thing going.

# The end.... just kidding, let's figure out how to cheese these tools
So it seems like to me that one thing typically creates better results with a few exceptions: parameter count. It seems the larger models did better, so we are going to start there and see what we can do. From now on, I am just going to run tables with test iterations of engineered prompts. I will see what works best and reveal some of how I did it. 


### Table: Attempt#1

{{<table "table table-striped table-bordered">}}
| Test | A1  | A2    | E1    | E2  | R1   |
| ---- | --- | ----- | ----- | --- | ---- |
| T1   | 4%  | 0%    | 100%  | 6%  | 100% |
| T2   | 0%  | 4.84% | 25.1% | 0%  | 100% |
| T3   | 0%  | 8%    | 3%    | 0%  | 38%  |
| T4   | 0%  | 0%    | 100%  | 0%  | 100% |
| T5   | 82% | 91%   | 100%  | 46% | 100% |
{{</table>}}
Okay, so this test gave me lots of info. It seems that two things became very apparently true. Fully generated text like in R1 is always going to fault given this method. As well as text that was genetically edited, and then regenerated to hide its generation will likely result in a fault as well. All that being said, my next test will just be using new organic written blobs to see if it will trigger anything.

### Table: Attempt#2
{{<table "table table-striped table-bordered">}}
| Test | C1  |
| ---- | --- |
| T1   | 23% |
| T2   | 0%  |
| T3   | 0%  |
| T4   | 0%  |
| T5   | 18% |
{{</table>}}
Well there we go, that's about as good as it's ever going to get. As far as I am concerned, at least. I do have to say that the last tool on my list, is an impressive piece of software. It has a superb method of checking, and my thoughts are that it's likely not just checking for repetitive phrases. My best guess is that it is using a model of its own to see if it resembles something else a human had written.

## Outcome
So let me break down how I gamed the system. It's not all that much of a one-size-fits-all solution to detection. It's more of a dynamic case-to-case idea, where you need to change and refactor the inputs and prompts to get the result you are looking for.

The first thing I have to say is that to even attempt this, tricking the detector, you need to write the text that you want to have cleaned up to make sure it isn't detected. That means that if you somehow want to come up with a full-fledged essay using a generation platform alone, I'd go back to the drawing board, which almost certainly will get the text read as AI being used. There is one tool in my testing that was very hard to convince legitimacy too, and if that's the test you want to beat and want to die on the hill of full generation, you will have to refactor the prompt so many times that it would have been easier to just write the stuff yourself.

### Prompt Engineering: 
My strategy on the attempts to beat these AI detection tools was that of some fairly simple prompt engineering coupled with carefully selected feeder data. It proved very important to aim the generation at pre-written blobs to get the lowest %AI in detection. This idea was proven further by the fact that the two text blobs from authors that I was using still did worse than my writings. I have a feeling that is probably due to how these models were trained and for that matter how the detection model (assuming they use some kind of ML) is trained. 


#### Simple prompt engineering concept:
What you want to do is find a model that you can add system prompts too, that or send two prompts to get the intended result. Here is an example:

So if you want to get an LLM to make you a prompt you can use this thought process, although I didn't make or use this part, or the second part really, these were written into Rez0_'s Metaprompter script. As he mentions, they work well and are a great basis for creating a good system/pre-prompt 

```
Persona: You are a super intelligent prompt writer.

Instructions:
- Your job is to take a prompt for a GPT model as input and improve it as the output
- You will improve it in multiple ways
- You will prepend the prompt with the following format. This will be placed before the original prompt. You will replace anything in brackets with appropriate context for the prompt

```

This is a modified version of what is in Rez0's script, since his was guided more at coding I altered and/or removed the parts that would have misguided us here.
```
Persona: {{insert the best persona to answer the question as an expert}}

Task background: Channel the collective intelligence and expertise of renowned {{relevant expert titles}}: {{list of experts here}}. By embodying their knowledge and experience in {{relevant field of study}} provide me with highly intelligent and informed responses to my questions. Use insights gained from their contributions to {{their works}} to address my inquiries effectively and comprehensively. 

Task: {{insert user's original prompt here}}
```




# Conclusion
Large language models, and AI these days as a whole, are not going away, and since the whole "you won't have a calculator in your pocket" thing seems to have aged terribly, we should likely learn how to use, understand, and know the limitations of these things. Condemnation of GPT usage is also not the answer, especially since the models improve at a rate much faster than any detection tool will be able to keep up with. So obviously if you came here for the tool to use, it's my T5 option, but really, why are you checking this stuff? Do you think that people cannot already have this in their pockets? Maybe the answer is to ban pockets...


###### tools
https://gptzero.me/ \
https://contentatscale.ai/ai-content-detector/ \
https://quillbot.com/ai-content-detector \
https://writer.com/ai-content-detector/ \
https://www.zerogpt.com/ \
https://www.scribbr.com/ai-detector/ \

Metaprompter:
https://github.com/jthack/metaprompter

