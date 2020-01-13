# Disclaimer

The following document is based on [notes from Jean-Yves LeBoudec](https://ica1www.epfl.ch/PS_files/paper.htm).
With his permission I formatted the notes (and fixed some typos).
All credit lies with him.

---

Writing a paper? Please check these guidelines. First answer the
following quiz.

# Quiz 1

## Q1

1.  My readers will carefully read my paper from the first sentence to the last.
2.  My readers will read the abstract carefully and, if interested, will dive into selected portions of the paper.
3.  No one will read my paper anyhow.

## Q2

1.  On page 2, I introduce the variable τ, and I use it again on page 13. My readers will remember what τ is, otherwise, why would they read my paper?
2.  On page 2, I introduce the variable τ, and I use it again on page 13. Since it is a long way from the definition to the next use, I put a list of variables at the end of the paper.
3.  No one checks the mathematical formulas anyhow.

## Q3

1.  The captions of my figures are terse. I assume my reader will look at the figure exactly when my text directs her to do so.
2.  My reader may look at the figures before reading all the text, just to get a feeling for the paper. Therefore I put captions that are as self-contained as possible.
3.  I never put figures. It is a pain to put them into Latex and no one looks at them anyhow.

[Now analyze your answers to Quiz 1](#analyze-your-answers-to-quiz-1).

# Quick check list
You are coming to discuss a paper, slide show or poster draft with me.
Before doing so, please check the following list. If some items are not
clear, you may want to read the rest of this document.

1.  You support random access.
2.  You define concepts once and at the right place.
3.  The abstract (in condensed form) and the introduction (in more details) entirely define what is in the paper (problem solved, limiting assumptions, main features of the solution). The reader will not discover hidden assumptions later in the paper.
4.  The structure of the document is clear from the section, subsections and paragraph titles.
5.  One single concept has a single name (no synonyms).
6.  You use the scientific method to draw conclusions.
7.  All simulation parameters are described and their values are given.
8.  The reference list is up to date.
9.  Figures and tables are stand-alone.
10. You use Latex.
11. Pages and sections are numbered.
12. You spell-checked the draft and you have an appointment with Holly to hollify the final version.

## For slides and posters

13. You avoid the two big mistakes.
14. You use the right tool.
15. You explain by example.
16. You give a complete view of your solution.
17. Slides are numbered.

# General guidelines

## You write for human beings

1.  Think about your reader. Who is she? Is she assumed to be an expert in computer networking or not?
2.  Help your reader. Even if your reader is an expert in your field, he is not* an expert in your work. You have spent the last months or years working on this project, but your reader has not. Please help your reader get the overall picture in place quickly. Reading technical papers is hard, is much less fun than reading novels, so please be kind to your reader (who may be your reviewer\...). Make it easy to understand whether every point you are making is
    -   an assumption,
    -   a review of existing work,
    -   your invention.
3.  Come to the point quickly. Do not spend your and the reader\'s time    about contorted introductions. If you are writing a paper about a congestion control protocol for audio applications, and your target journal is IEEE transactions, do not spend a paragraph explaining why internet telephony is important. *But do not forget to explain what your problem is.*

## Organize the information you are delivering

This is the most difficult part -- if you master the two points below,
you are in good shape.

1.  Define concepts once and at the right place.

    Readers expect to find things at the right place. System
    description, review of state of the art, simulation setup,
    simulation results are all different things. They should appear in
    well defined sections, and only once. DO NOT define or explain the
    same thing twice. This gives a non professional look, and is likely
    to be inconsistent as your paper evolves.

    \
    *Don\'t*

    > In Section \"Simulation Setup\": Nodes periodically broadcast
    > HELLO messages in order for nodes to build their ZRW routing
    > tables. When a HELLO message is sent, the HELLO timer is reset.
    > The value of the HELLO timer is 1 s

    \
    *Do*

    > In Section \"3.2.2 Description of Protocol\": Nodes periodically
    > broadcast HELLO messages in order for nodes to build their ZRW
    > routing tables. When a HELLO message is sent, the HELLO timer is
    > reset.\
    > In Section \"5.1 Simulation Setup\": the HELLO timer (see Section
    > 3.2.2) is equal to 1s


    In a subsection called \"Solution Overview\", do not give general
    considerations about things you left for further study. In a section
    called \"Numerical Results\" do not explain the protocol you are
    simulating. In Section \"Protocol Walkthrough\" do not justify why
    you leave some function out of scope.

2.  Support random access.

    Many readers, among them reviewers, will jump from figure to figure,
    or from section to section. Many will read the captions before
    reading the sections they are in. Be aware of that.

    Now I hear you say: how can I combine random access without
    repeating the same thing again and again? Well, that\'s precisely
    what you should target: give enough information for the reader who
    does random access, but do not repeat the same thing again and
    again.

    A figure caption should give enough accurate information to make
    random access possible and pleasant to the reader. Do not be afraid
    to have long captions. In the caption, point to precise locations in
    the paper where the reader can find all details, if necessary.

    \
    *Don\'t*

    > (caption of Figure 5). Simulation results for a 500 node network
    > with Pause-Time on the x-axis.

    Your reader may misunderstand which network you are simulating here.
    She needs a precise definition of the network and the parameter
    Pause-Time. Otherwise, she may understand something completely
    different than you think; for example: Figure 5 is about the same
    network as in Figure 3, but with 500 nodes instead of 100. (In this
    specific example, the networks in Figures 3 and 5 are not the same;
    this is clear from the full text \-- it should also be clear to a
    reader who jumps from figure to figure).

    \
    *Do*

    > (caption of Figure 5). Simulation results for the network of
    > Figure 4 with 500 nodes. Total throughput versus Pause-Time
    > (defined in Section 6.7.3)



Here are a few observations to help you reach these two objectives.

-   Make sure all notation you use is easily identifiable. If you talk of parameter α at great length in Section 5.3, and α was defined somewhere in the middle of a paragraph in Section 2.3.4, then you have a problem. It will be very hard for a reader to locate the meaning of α. In such a case, list all your global important notation in a table or a very visible paragraph.
-   Avoid using synonyms. Synonyms are great when used by Dostoievski in a novel, but not in a technical document.

    \
    *Don\'t*

    > Node A forwards the packet using the fixed address since the
    > destination is reachable by ZGW. \... If the destination is in the
    > ZGW routing table, node A should not use the location information
    > \.... When the destination is in the ZGW reachable area, the TTL
    > field is updated differently \...

    Your reader will wonder: is there a difference between the three
    terms \"reachable by ZGW\", \"in the ZGW routing table\", \"in the
    ZGW reachable area\". It may be obvious to you that they are the
    same, but this is probably not so to the reader.

    \
    *Do*

    > The node builds its ZGW routing table using the fields heard in
    > the Hello messages. \...Node A forwards the packet using the fixed
    > address since the destination is in the ZGW routing table. \... If
    > the destination is in the ZGW routing table, node A should not use
    > the location information \.... When the destination is in the ZGW
    > routing table, the TTL field is updated differently \...

    Once you introduce a name for an object, stick to it. Accept the
    repetitions that this may cause.

-   Give your justifications at the beginning of the paper (for major justifications) or of the section (for minor justifications). Do *not* give them on the fly, as needed. Once you have justified a choice, do not justify it again -- this weakens your justification.

    \
    *Don\'t*

    (head of section 5)

    > We study three loss model: fixed loss probability, time varying
    > loss probability and the Gilbert loss model. The first one
    > discards each incoming packet with the same probability. The
    > second loss model provides more variable network conditions where
    > the packet drop probability alternates between high and low while
    > the same average drop probability is maintained. The congestion
    > control protocols frequently have to adjust their sending rate,
    > putting more emphasis on the transient behavior of the protocols.
    > The last one produces highly correlated losses.


    (subsection 5.3: Performance with Gilbert Model)

    > The Gilbert loss model is not intended to closely model realistic
    > network conditions found in the Internet. It is merely used to
    > analyze how the mechanisms perform when the assumption of packet
    > loss independence is not met. The model remains in its current
    > state for a fixed amount of time, τ=10 ms, after which a random
    > experiment is performed to see whether a state change should
    > occur.

    \
    *Do*

    (head of section 5)

    > We study three loss model: fixed loss probability, time varying
    > loss probability and the Gilbert loss model. The first one
    > discards each incoming packet with the same probability. The
    > second loss model provides more variable network conditions where
    > the packet drop probability alternates between high and low while
    > the same average drop probability is maintained. The congestion
    > control protocols frequently have to adjust their sending rate,
    > putting more emphasis on the transient behavior of the protocols.
    > The last one produces highly correlated losses. It is not intended
    > to closely model realistic network conditions found in the
    > Internet. It is merely used to analyze how the mechanisms perform
    > when the assumption of packet loss independence is not met.


    (subsection 5.3: Performance with Gilbert Model)

    > The model remains in its current state for a fixed amount of time,
    > τ=10 ms, after which a random experiment is performed to see
    > whether a state change should occur.

-   Do not introduce major building blocks in the middle of the paper.

    \
    *Don\'t*

    In Section 5 (detailed description of the protocol):

    > The estimation procedure may be \`\`stuck\" if the source does not
    > have a neighbour that has older information than self. This
    > happens in irregular topologies. The solution that we adopt to
    > solve this problem is proposed in \[22\] and\[23\]. The source
    > thus computes the weighted sum of increase components and applies
    > the following equation\...

    \
    *Do*

    In Section 2 (overview):

    > The estimation procedure may be \`\`stuck\" if the source does not
    > have a neighbour that has older information than self. This
    > happens in irregular topologies. In our protocol, we adopt the
    > solution in \[22\] and\[23\].


    In Section 5 (detailed description of the protocol):

    > As mentioned in Section 2, the source uses at this point the
    > recovery procedure defined in \[23\]. It computes the weighted sum
    > of increase components and applies the following equation\...

-   Give all your assumptions at the beginning of the paper. Do *not* introduce them one by one, as you need them.

### Be scientific

1.  Use the scientific method to draw conclusions. The scientific method means that you do not draw a conclusion before verifying what you are going to say; in short:

                do
                   {
                        define hypothesis;
                        design experiments;
                        validate
                    }
                until (validation is OK)

    \
    *Don\'t*

    > (In Section \"Simulation Results\"): The normalized routing load
    > is shown in Figure 4. We see that protocol B has much less
    > overhead than protocol A. Protocol A frequently uses flooding as a
    > means to build or repair broken routes, which causes a large
    > overhead.

    The flaw is that you *interpret* Figure 4 when you say that protocol
    A has more overhead because it uses flooding. The only thing the
    figure says is that protocol A has more overhead. Your
    interpretation may be right (it might also be wrong, for example the
    larger overhead might be due to the setting of a Hello timer). The
    only thing we can say is that the figure leads you to pose as
    *hypothesis* that protocol A has large overhead due to flooding. The
    next step is to design an experiment that will confirm, or infirm
    that hypothesis.

    \
    *Do*

    > (In Section \"Simulation Results\"): The normalized routing load
    > is shown in Figure 4. We see that protocol B has much less
    > overhead than protocol A. Protocol A frequently uses flooding as a
    > means to build or repair broken routes. We pose as hypothesis that
    > this might be the cause of this large difference. To test this
    > hypothesis, we designed the following experiment. We measured the
    > performance of protocol A after setting the flooding frequency
    > parameter to a high value. We used a low mobility scenario where
    > route breaks are rare. Figure 5 shows that the routing overhead of
    > A and B are now comparable, which confirms our hypothesis.

2.  All simulation parameters are described and their values are given. It should be possible for an independent researcher to reproduce your results. Put your simulation code on the web.
3.  There are no ambiguities. All graphs and tables have units. If you use the word \"billion\", say whether is 9 or 12 zeroes.
4.  Make sure you spend enough time to scan the literature and are aware of the state of the art. You must incorporate in your state of the art the findings published in IEEE and ACM journals and conferences -- ignoring a single paper there may be fatal. Also use Citeseer, the Web of Science\... and Google.

    Your reference list should be up to date. Many reviewers will fist
    look at your list of references to see if you are up to date. If an
    important reference is missing, your paper is probably already
    rejected.

# Make an abstract

The research is done, you now want to finalize your findings in a paper.
The first step is to do an abstract. If you succeed, go ahead with
writing the paper. Else, you probably want to do some more research.

The abstract should contain the following parts.

1.  What is the problem?
2.  Why is it a problem?
3.  Why is it important to solve it?
4.  Give your main findings, the ones you want people to remember.

# Make a production plan

The abstract is done, you now want to finalize your paper.

1.  Make a rough time plan. Estimate when you have completed what. This seems magical, and when you do this for the first time, you may find that it is non-sense to make a time plan when everything is so uncertain. But when you have more experience, you will be surprised to see that it is possible to do a time plan. The time plan serves two goals:
    -   reduce your stress: By defining smaller pieces, you see progress and you gain confidence.
    -   set priorities: With a time plan you become aware of where you spend time and of what you can and cannot achieve.

    A time plan is not a strict schedule. You need to adjust it at least
    once a week. It evolves as difficulties arise (most frequent case)
    or when the job is easier than expected (less frequent case). You
    may wonder: why bother keeping track of a moving time plan? Well,
    this is precisely for keeping track. This will help you decide about
    your paper, rather than let things decide for you.
2.  Emergency costs time. If you have a strict deadline (call for paper) then put some buffer in your time plan. Plan to deliver the paper 3 days before the deadline. It is unwise to believe that your paper is  more competitive because you worked on it until the last second. Delivering the paper in advance will leave you relaxed, and this will feel in the paper. You will avoid wasting time due to busy FTP server, incompatible fonts, network outages, snow storms, hard disk crashes, last minute emergency with your TA duties, etc.
3.  Plan for a final pass (see below).

# Write the paper

1.  Do a map, containing all the ideas and points you want to make
2.  Now write a sketch. It contains the contents of all sections in a few words. Try a structure (= break the story into several pieces). Do not worry too much about section sizes at this point, you will tune this later.
3.  One section, or part of section, is the state of the art. Be very careful about that one -- a deficient state of the art accounts for a large fraction of rejected papers.
4.  Write the sections. This will take you many days. You will have to iterate on the previous points.
5.  Write the conclusion. The conclusion should not bring any new piece of information about your current work, it should only summarize, or put in a different perspective, some elements which were explained earlier in the paper. You may additionally open up to areas of interest, or related problems that you intend to tackle (but will you really?).
6.  Write the introduction. The introduction should explain the same points as the abstract, with more details. If the state of the art is not too long, put it in the introduction, else in a section of its own.

# Style

Now it is time to think of your writing style.

1.  Introduce one point per sentence, not more. Break sentences into several, if needed.

    \
    *Don\'t*

    > We prove that, in the limit of infinite power, the fairness index
    > tends to 0. We verify numerically, on a large number of random
    > networks, that unfairness does occur with realistic power
    > constraints, which is a generalization of results from \[ZGOMO\]
    > saying again that this unfairness property is not a problem of UWB
    > but rather of the performance metric.


    The last sentence makes two points: (1) the unfairness that occurs
    at the limit also exists in reality (2) the problem reported in
    \[ZGOMO\] is explained by this general result.

    \
    *Do*

    > We prove that, in the limit of infinite power, the fairness index
    > tends to 0. We verify numerically, on a large number of random
    > networks, that unfairness does occur with realistic power
    > constraints. This generalizes the problem reported in \[ZGOMO\]
    > and shows that is not a problem of UWB but rather of the
    > performance metric.

2.  Streamline your sentences: remove unnecessary words.

    Replace

    > When the ZMRP mechanism is employed, nodes send only one message
    > per round. We have that the cost per round is XY/2.

    by

    > With ZMRP, nodes send only one message per round. The cost per
    > round is XY/2.

    Avoid contorted expressions.

    Replace

    > We can observe that protocol B greatly reduces routing overhead
    > compared to protocol A.

    by

    > Protocol B has much less routing overhead than protocol A.

3.  [Also see Henning\'s Schulzrinne\'s recommendations](http://www.cs.columbia.edu/~hgs/etc/writing-bugs.html), but do not follow his recommendations on inline enumeration and bullets.

**The following style advice was added by [@timueh](https://github.com/timueh)**

4. Once you have written a fair amount of text, put it aside. Leave it untouched at least for a day.
5. When proof-reading, mumble or, better yet, read out loud. Speaking comes naturally to humans, but writing is a cultural trait. Writing means *to speak through words*. Mumbling turns writing into reading: the brain processing sound waves.
6. Ask others to proof-read your paper.
7. Remove unnecessary words not in the first draft, but in the close-to-final one.

# Final pass: Remove

You have written your paper, or at least you believe so. Well, you now
need a final pass. The goal is now to remove* things that are not needed.

1.  Be critical, see your work with the eyes of an external reviewer: is everything you are writing in the paper really interesting?

# Slides and posters

1.  Why do you give a talk? People can have your paper in the proceedings, so you must add value to reading the paper. At the end of your talk, the audience should have learned something, even if they never read the paper in detail.
2.  The two big mistakes are
    -   Too superficial: you explain at great length why you do your stuff, why it is great, etc, but at the end the audience does not have much more information than by reading the abstract of your paper.
    -   You lost your audience: because you do not have time to explain all aspects of your paper in detail, you quickly throw at people an indigestible list of concepts and equations that no one  understands. You think you impress your audience in this way, but you don\'t.

    In both cases you are boring.

3.  To avoid both mistakes, you have to make a choice of which aspects you want to explain in detail. Then do explain them in detail, and position them with respect to the big picture. Plan your time carefully. In general, count 1.5 - 2 min per slide.
4.
4.  Explain by example. Human brain is not a Turing machine; we learn by example and imitation. If you have defined a complex, smart protocol, imagine a number of typical scenarios, which can illustrate all the beauty of your concepts, and explain one by one how the mechanisms work on these scenarios.
5.  However, do not explain only by example. Also give the global picture. This gives the audience the warm feeling that there *is* a global picture.
6.  If you show an equation, make sure the audience will have enough time and information on the slide to understand it. Otherwise, why do you show it? (do not do mathematical intimidation). Displaying equations in a slide show is like showing love scenes in a movie -- you can do it, but be careful and do not abuse\...
7.  You think that since you have defined parameter x in slide 2, the audience will remember at slide 25 what x stands for. Well, you are probably wrong. Do not assume that your audience will have in mind the complete list of parameters that you defined in the paper.
8.  Use the right tool. The tool influences your slide show.

    Make sure you master *both* Latex and Powerpoint or equivalent. Only
    then you will be able to decide which tool is the best.

    In general, you tend to not do enough pictures.

    ~~Do not waste your time writing equations in Powerpoint \--
    instead, cut and paste equations from the pdf or ps of the paper
    that you have already written (with Latex), or even better, use
    TexPoint.~~ Use the newer powerpoint equation editor, which uses the
    Latex syntax.

# Analyze your answers to Quiz 1

-   If you have a majority of 1s, then answer [Quiz 2](#quiz-2).
-   If you have a majority of 2s: you have understood a fundamental fact about your reader. Go on with reading this text and give me your feedback.
-   If you have a majority of 3s: you should consider consulting a psychologist (see [here](https://psychologue-psychotherapeute-bruz.fr/) for a good one), or taking another job.
-   If you have one answer of each type, take [Quiz 1](#quiz-1) again.

# Quiz 2

Are you a genius?

1.  Yes.
2.  I don\'t know.
3.  No.

If your answer is 1, congratulation. Your findings are so great that
readers will very carefully read all of your text. You do not need to
bother about writing style. This document is not for you.

If your answer is 2 or 3, [take Quiz 1 again.](#quiz-1)

# Credits
Thank you to the many authors who helped me formalize these guidelines.
Thank you to J.
