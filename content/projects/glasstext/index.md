---
title: "Glasstext"
summary: A browser tool that measures English prose and shows the arithmetic behind every number, including where each one breaks.
date: 2026-10-14
authors:
  - me
tags:
  - text-analysis
  - readability
image:
  alt_text: "Glasstext analyzing a bureaucratic sample paragraph, showing words per sentence, syllables per word, a warning that the readability formulas disagree by 22.2 grades, and the first three formula scores"
---

{{< toc mobile_only=true is_open=true >}}

Glasstext started as a side project, something I built for fun. It is a small tool that runs in the browser, measures a piece of English writing in several ways, and shows how it arrived at every number. Along the way, it changed how I think about reading.

## Where it started

For most of my life, I judged writing by feel. A text was boring, or complicated, or it had that dense quality you find in scientific papers, and the impression changed with whatever I happened to be reading. I never thought there was much more to say about it.

Then I came across readability research. For much of the twentieth century, researchers tested readers on passages, then fitted equations that predict how hard a text is from things you can count, such as the length of its sentences and the length of its words. I did not know people had tried to put numbers on this, and I found it fascinating.

What bothered me was how those numbers usually reach people. Most tools give you a score, say a grade level of 11.4, and stop there. You cannot see which equation produced it, from what counts, or when it stops being trustworthy. So I built one where you can.

## How it works

You paste or type English text, open a .txt file, or load one of the samples, which range from plain to bureaucratic. The results are spread across five tabs:

- **Readability:** six classic formulas (Flesch Reading Ease, Flesch–Kincaid, Gunning Fog, SMOG, Coleman–Liau, and the Automated Readability Index), with a warning when they disagree.
- **Vocabulary:** how varied the word choice is, from the simple type-token ratio to MATTR and MTLD, which correct for the length of the text.
- **Style:** sentence rhythm, the longest sentence, passive-voice candidates, nominalizations, and hedges.
- **Distribution:** the Zipf and Heaps curves, which show why simple vocabulary measures depend on length.
- **Filter lab:** a hands-on look at why word filters block innocent words, known as the Scunthorpe problem.

Any number can be opened up to show the formula, the counts that went into it, the paper it comes from, and the cases where it breaks. A Learn page walks through the reasoning behind each metric. Everything happens in the browser, and there is no backend.

## What I learned

The first lesson was the one I started with: readability can be measured, at least in part. What surprised me next was how simple the recipe is. All six formulas use the same two ingredients, sentence length and word difficulty, and differ mainly in how they measure and weigh them. That explains why they usually agree, and why their agreement proves less than it seems.

The second lesson was how much they miss. Shuffle the words of a sentence into nonsense and every readability score stays the same. The formulas cannot see word order, whether one sentence connects to the next, or whether the reader already knows the vocabulary. A cardiologist reads a cardiology paper faster than a novel, and no formula knows that. So the feel I relied on before still counts. It picks up things the numbers cannot reach.

That leads to the lesson I would pass on to anyone who uses these tools: the score is a symptom, not a target. The formulas reward short words and short sentences, so you can improve a score by swapping a precise term for a vague one, or by cutting a sentence that explained itself. The number gets better and the writing gets worse.

On the building side, I learned that the unglamorous parts decide the result. When two readability tools disagree, the cause is rarely the equation. It is usually how each tool splits text into sentences and counts syllables. Counting syllables in English is harder than it looks: "wind" has one and "winded" has two, and native speakers still argue about "fire" and "hour". I also learned to measure a rule before trusting it. Treating "oe" as two syllables sounded reasonable, but words like "toe" and "shoe" outnumber the cases it fixed, and the measurements showed it made the counter worse. So I took it out.

## Design choices

The first choice was to show the working behind every number. If a tool asks you to trust a score, it should let you check it.

The second was privacy. People paste drafts, notes, and unfinished work into tools like this, so I wanted a guarantee rather than a promise. The page has no analytics, no outside scripts, and no backend, and its content security policy blocks every network request. The browser itself stops the text from going anywhere. Open the network tab after the page loads, and it stays empty.

The third was to measure the tool's own weak points. The syllable counter agrees exactly with the CMU Pronouncing Dictionary on 91.98% of 117,486 words, and comes within one syllable on 99.77%. I cross-checked the formulas against textstat, an independent Python library, and that turned up a small error in its documentation: it prints the Coleman–Liau coefficient as 0.058, where the published value is 0.0588. Known mistakes, such as a sentence ending in "a.m." that does not get split, are kept in the test suite as they are, so a future fix shows up instead of happening silently.

The last was to leave things out when I could not do them properly. The Dale–Chall formula is missing because I could not find a copy of its word list I trusted, and an approximation under a published name would look more authoritative than it is. The Filter lab shows what matched and why, but it never says whether a text is clean or offensive. That is a judgment for a person, with context.

## Try it

Glasstext is free to use and open source. The code, the tests, and the full list of references are on [GitHub](https://github.com/meherbejaoui/glasstext).

{{< button url="https://www.meherbejaoui.com/glasstext/" new_tab="true" >}}Open the tool{{< /button >}}
