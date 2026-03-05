WEBVTT



1

00:00:02.740 --> 00:00:10.379

Technologic: You probably do need a laptop for this. I mean, I guess I can put it up on the screen. I wrote a… I wrote a memo. Oh, okay, I can get it out.



2

00:00:10.700 --> 00:00:15.629

Technologic: I… so, anyway, for today, I decided that we should kind of, like.



3

00:00:15.910 --> 00:00:29.610

Technologic: I wrote a memo for us to kind of, like, go over the last two weeks, and then after that, I was like, you know, we didn't go over the prizes for the hackathon, so I just wanted to do that. So that's kind of, like, the structure for today. So I linked the…



4

00:00:30.000 --> 00:00:32.950

Technologic: memo here, but then I'll also…



5

00:00:33.730 --> 00:00:37.989

Technologic: share on the screen for the folks who don't have their laptop. Do you want to join us?



6

00:00:40.330 --> 00:00:41.080

Technologic: Okay.



7

00:00:44.890 --> 00:00:46.610

Technologic: You can read. Okay.



8

00:00:49.510 --> 00:00:51.000

Technologic: Do you know if consumption?



9

00:00:51.360 --> 00:00:54.109

Technologic: He's on Google Mist. Oh.



10

00:00:54.460 --> 00:00:58.440

Technologic: Oh, yes sir. Oh, yeah, yeah.



11

00:03:20.460 --> 00:03:26.580

Technologic: Question. This refers to a GPM that was at the one we saw at the start of the sprint? Yeah, good personal.



12

00:03:55.820 --> 00:03:56.940

Technologic: I'm sweet.



13

00:03:57.500 --> 00:04:04.630

Technologic: True, true. It's just, missing the man.



14

00:04:05.250 --> 00:04:13.180

Technologic: Wow. Oliver's? What was Oliver again? Completely different. No, no, it was like, it was like an Indian dude. Indian dude, yeah.



15

00:04:15.300 --> 00:04:17.059

Technologic: The badger returned to me.



16

00:04:21.350 --> 00:04:22.290

Technologic: Okay.



17

00:04:22.420 --> 00:04:25.240

Technologic: Anyone need more time? One minute.



18

00:05:25.580 --> 00:05:28.449

Technologic: Yeah, I'm good. Anybody else? I'm good? Yeah.



19

00:05:29.410 --> 00:05:31.440

Technologic: So yeah, I kind of wanted just to, like.



20

00:05:32.010 --> 00:05:39.270

Technologic: clear, like, acknowledge some of the feelings that I've heard and clear the air. And so, I just thought it would be a good time to kind of just, like.



21

00:05:39.890 --> 00:05:45.949

Technologic: saying, hey, I recognize what's been happening, and just kind of be able to talk about some of the things that



22

00:05:46.180 --> 00:05:59.019

Technologic: you know, have happened, and some of the concerns that you guys still have. And I think, yeah, I think, you know, me and Jay are gonna be, you know, we're fully open about this, and I think last time, I realized that, like, even though we kind of, like, put it out there, like, halfway through the sprint, but, like.



23

00:05:59.150 --> 00:06:05.440

Technologic: Maybe some of the… issues with AppCloud, I think we did it after, like, everyone kind of presented already.



24

00:06:05.640 --> 00:06:25.239

Technologic: folks might have been tired, or whatever, after, like, an hour and a half meeting. That probably wasn't the best timing. So, if we want to open that, you know, book again, I'm happy to talk about it there. Also, I feel like we weren't very clear on, like, what was happening with DAFT, open source, like, DAF felt, right? Yeah, just wanted to just give February the chance to…



25

00:06:25.520 --> 00:06:28.629

Technologic: You know, just make sure that everyone knows what's going on. Yeah, yeah.



26

00:06:28.760 --> 00:06:42.229

Technologic: I do… something still doesn't feel clear to me, because it seems that now we say that, you know, the current direction of daft talk is maybe not the right approach, so we're going back to, like, daft and something experimental.



27

00:06:42.370 --> 00:06:49.759

Technologic: Are we pausing, like, DAF Cloud as well? Like, all current, open loops and DAF Cloud, we just, like, pause it first?



28

00:06:50.100 --> 00:07:05.779

Technologic: Yes, so the idea is that, like, I think for DAF Cloud as an ingestion, purely as an ingestion product, which is, like, S3 or Data Source 2, like, a vector database or, like, a Postgres or whatever, yes, we are policy development. Everyone else is… everyone is, like.



29

00:07:05.930 --> 00:07:13.669

Technologic: not touching it for now. Yeah, and so I think the key thing we want to leverage is, like, we want to think about what things we can leverage to move faster.



30

00:07:13.670 --> 00:07:23.189

Technologic: on what does make sense today, and so that's, like, stuff like the platform, observability, everything else we've built that we can leverage. So, all the work we've done with SOC 2, the stuff we've done, like.



31

00:07:23.190 --> 00:07:39.829

Technologic: with, like, Chris and Oliver and G building, like, an amazing infrastructure deployment platform. Like, those are all things that will make us move a lot faster. Right. The work that we might do for, like, you know, the click stack and observability, that is stuff that makes… I see, I see, I see. So, we're gonna reuse everything we can. Like, the stuff we built for inference, for example, all that is reusable.



32

00:07:39.860 --> 00:07:49.240

Technologic: Right. But the product itself, as in the face of a customer, that, like, what we found is that, one, is that



33

00:07:49.300 --> 00:07:54.720

Technologic: it's just not strong enough of a pain point relative to the other pains we'll have today. Yep. Right?



34

00:07:54.720 --> 00:08:12.879

Technologic: I think the world is very different, like, a year ago, when we talked about this problem. Yeah. I think it became pretty apparent during the sprint, too, right? Like, we indexed our entire thing pretty easily. Yeah. There was no, kind of, like, big pain point there. You know, you could 10x the volume in 100x, maybe, you know, it starts getting painful, but yeah, I think it became pretty apparent.



35

00:08:14.950 --> 00:08:15.610

Technologic: Yep.



36

00:08:16.020 --> 00:08:23.570

Technologic: should we do a small amount of work to, like, close down bits of DoveCloud that we don't need anymore? Like, stop paying for GPUs and stuff?



37

00:08:23.700 --> 00:08:33.039

Technologic: I think that's a good idea. I'm getting security reports. Yeah, actually, we can bring it down to the minimal thing. We should still keep the service running, because we still want to go through SOC 2 and everything.



38

00:08:33.150 --> 00:08:40.089

Technologic: But anything we don't, like, need, like, we're not even, like, spin down some of the tests to, like, run…



39

00:08:40.450 --> 00:09:00.170

Technologic: once a day instead again. Sorry, Sam, Colin. But then you can have the test run more or less often, or even once a week if you want, right? Just, like, minimal just for a show. That'll also help us with our, like, signal spill and stuff like that. Yeah. Yeah. I guess also a good opportunity to call out that, like, yeah, like, thanks everyone for putting effort into DAFCloud. I know.



40

00:09:00.280 --> 00:09:11.230

Technologic: towards the end of last year, it was, like, a big sprint, trying to get all the inference stuff in. I think a lot of it will still be useful, but yeah, I think, you know, we took a stab, and now we're trying to take a different stab at it. Yeah.



41

00:09:11.780 --> 00:09:20.859

Technologic: And I don't think it's too far off from what we have. It's… the key thing is that, like, we realize that it's just… we're not far enough at the value chain. Because the issue is that, like.



42

00:09:21.120 --> 00:09:34.189

Technologic: even if we ingest vectors into a database, right, folks are still struggling to figure out how to use it effectively. It's like, there's many steps removed from the value, yeah. And what we… I think… I think the thing we learned, and I think we proved out, is, like.



43

00:09:34.700 --> 00:09:38.150

Technologic: Maybe it was a half measure. I think we might have to go a full measure.



44

00:09:45.250 --> 00:09:46.780

Technologic: Have you any other questions?



45

00:09:47.860 --> 00:09:56.139

Technologic: So maybe another, like, little bit of context to add is, like, yes, we kind of want to adapt and explore, but I think we'll try and do it in, like.



46

00:09:56.420 --> 00:10:10.389

Technologic: in a limited time fashion, so it's kind of, like, next, like, 4 to 6 weeks, like, you can think about, like, either the month of February, or whenever we do the off-site, we're still trying to figure out. Like, I think that we'll discuss more on Monday details, but, like.



47

00:10:10.580 --> 00:10:32.870

Technologic: get daft in a place where it is also possible for the rest of the community to grow it better, but get some of the critical stuff that is locked on us, that we don't think the community can build. So let's, in the next month or so, get those things out. So, because also, if we pull the community in, we don't want to do it in a way which is not sustainable. We want… we still want the project to succeed. Also, if we kind of pull back a little bit, right, we'll see.



48

00:10:33.030 --> 00:10:55.410

Technologic: at the same time, kind of exploring on something new with, like, a smaller, more focused team kind of thing. But again, like, Sam and Jay will, I think, share more on Monday as well, as we go forward. I think the goal with DAF open source is really, like, this year, at least, how can we start growing it so that it's more than ourselves? That's going to be critical, right? Already, actually, I think I haven't shared this yet with the team, but the ByteDance folks shared with me a



49

00:10:55.490 --> 00:11:17.479

Technologic: kind of a list of people that are using it in production in China, it's substantial. Yeah. Like, Alibaba Cloud is actually adopting DAF now in their own, like, MR-like offering. Xiaomi is, like, leaning in, right? There's, like, a whole bunch of other Chinese companies that are pretty big that I didn't know what they were, but I switched them out. They are using it for images. I don't know why, but China loves their, like, images and video.



50

00:11:17.620 --> 00:11:33.389

Technologic: So yeah, there is a lot of usage and demand on the DAF side, and, you know, huge kudos to the team, like, that all kind of happened towards the end of last year, I would say. Yeah. And you see that reflected now in the activity on the GitHub, right? One thing I'm wondering about then is that,



51

00:11:34.180 --> 00:11:46.879

Technologic: We don't have to answer this now, but I'm wondering, because, like you say, it seems like there's a substantial, like, dark EMR thing happening in China, but we're not part of that at all, like, we're nowhere in, like, the revenue stream for that. Yes, well, and to…



52

00:11:47.220 --> 00:11:57.640

Technologic: I mean, very transparently, why is that in China they have adapt EMR thing? It's because in China, they've also chosen to lean in on Ring, right? Any skill's not in that bad, actually, either, basically, but they have…



53

00:11:57.840 --> 00:12:17.829

Technologic: most of these Chinese clouds have decided that Spark for, data stuff, and then Ray for, you know, multimodal AI stuff, right? And because they have Ray, now they're like, okay, let's slap down. I see. So, you know, I don't know if we can be a part of that value chain. Yeah. Just because, like, yeah, Ray… Any skill itself is part of that value chain. Yeah.



54

00:12:18.210 --> 00:12:24.439

Technologic: Yeah, it's tough. It is tough. I think the Chinese market is very difficult to monetize, you know? It's very difficult.



55

00:12:25.920 --> 00:12:32.860

Technologic: And I think over here, like, the multimodal aspect is very, I would say, different in China. I think over here, it's, like.



56

00:12:33.120 --> 00:12:49.940

Technologic: everything we see with multimodal is less about batch processing and more, like, real-time processing. Like, you want to generate images now. You want to, like, see what's in this document, like, right now. Yeah. And so, the form factor, I think, in the, like, Western market is very different than what we see in China. Yeah.



57

00:13:01.600 --> 00:13:03.560

Technologic: Any more thoughts?



58

00:13:03.670 --> 00:13:08.650

Technologic: Questions? All thoughts about that, but, like, I think it'll be derailing, so…



59

00:13:09.250 --> 00:13:12.020

Technologic: You talked about the target team.



60

00:13:12.120 --> 00:13:17.249

Technologic: Who presumably will get an answer to this sooner, but… No. Do we have a…



61

00:13:18.070 --> 00:13:19.799

Technologic: And Beyonce might just be both.



62

00:13:19.900 --> 00:13:24.690

Technologic: Do we have, like, a three-word description of what



63

00:13:25.410 --> 00:13:33.720

Technologic: the next step will be. Yeah, I think it's kind of a lot what we talked about, yesterday, actually. I think what we're seeing is, like.



64

00:13:33.890 --> 00:13:42.529

Technologic: I think we need to be able to, like, kind of like what I mentioned here in the memo, which is, like, we need to have our own measurable metrics. I think the key thing is, like.



65

00:13:43.930 --> 00:13:54.920

Technologic: we need to be able to go to, like, Notion again, like, that one… like, we had a meeting with Notion yesterday, and I think we learned quite a bit. I think we, like, learned about, like, how they kind of see things.



66

00:13:55.630 --> 00:13:58.569

Technologic: But, like… At the end of the day.



67

00:13:58.710 --> 00:14:16.320

Technologic: it's much better if I can… we can go to them with, like, hey, this is what we do, this is how we measure search quality. We can show you what that looks like, and it's under this tight budget. Right, and that's actually a product they can buy and try. Yeah, they closed the meeting by saying that was a lot of information. So, we, like, painted this vision, and, like.



68

00:14:16.320 --> 00:14:31.549

Technologic: agent bill stuff, and it doesn't fucking matter in the end, right? What matters is, like, saying, hey, we have a product that does this, and it's a lot of time. I think it's the same thing you told me before, where, like, we can't automatically choose the right model embedding, because the eval has to happen on the customer side, right? We can't do the eval. Exactly.



69

00:14:31.950 --> 00:14:33.540

Technologic: So it's the three-word, like…



70

00:14:34.020 --> 00:14:48.680

Technologic: fast enterprise search or something. Fast enterprise search. Fast third-party enterprise search for agents. But at the end of the day, like, I think what we need to do is be able to build it, and then show quality. And I think the way we, like…



71

00:14:48.680 --> 00:14:58.989

Technologic: go up the value chain. Rather than being like, oh yeah, we have this, like, one recall metric for a chunk, we can say, hey, we can actually pull this percentage of recall for the relevant select threads.



72

00:14:59.400 --> 00:15:07.850

Technologic: Right? We can pull the relevant, like, Notion talks for this much. We make sure that the information that we're in the search results are the most relevant, and this is how we measure it.



73

00:15:08.090 --> 00:15:18.100

Technologic: And I guess the, the idea, almost, behind why, like, this is this, like, we can build this and not compete against every other fast enterprise search company out there.



74

00:15:18.200 --> 00:15:29.010

Technologic: It's because of, like, the kind of documents or the kind of integrations. Unstructured documents, like videos, transcripts, like, all of that is, like, what is in our forte and in our DNA, and part of this is, like.



75

00:15:29.400 --> 00:15:47.090

Technologic: we need to just blow everyone's out of the water. Yeah. Like, I think we… the way I say it is, like, I was telling Jay this, I'm like, dude, I've been optimizing systems for 15 years. Yeah. I can, like, look at a blame chart and, like, what's happening. Yeah. Right? Yeah. I don't know Agent Evolve, I don't know this stuff, right? I don't. Yeah. Right?



76

00:15:47.090 --> 00:16:02.500

Technologic: But, like, if you give me, like, a systems problem, I have taste. Yeah. Right? And we have to be true to our DNA. I really do think there's a world in which, like, this stuff is, at the end of the day, the thing that matters, right? Like, the faster you can search, the more data you can search, the more data gets to the agent.



77

00:16:02.500 --> 00:16:14.250

Technologic: I think there's ways we can, like, tie it in, and really go around waving the banner of, like, we have just the fastest way to search through enterprise data, and at the end of the day, I do think it matters. It really depends on how we, like, go to market.



78

00:16:14.300 --> 00:16:15.479

Technologic: And does this…



79

00:16:15.660 --> 00:16:19.479

Technologic: To tie it back to the conversation from last week, does this put us in the token path?



80

00:16:19.570 --> 00:16:37.570

Technologic: Yes. Yes. Because we're not, like… the thing that Notion, like, initially thought we were going to bring to them is, oh, we're going to ingest data into their vector DB, and then they do the search, right? But in this case, rather than us being Big O of, like, data ingested, we want to be big O of data processed and searched.



81

00:16:38.780 --> 00:16:40.419

Technologic: What does imitopen cloth mean?



82

00:16:40.530 --> 00:16:46.050

Technologic: That when people spend dollars on tokens, we take a card of the account. Yeah.



83

00:16:46.180 --> 00:16:50.000

Technologic: So, essentially, every time someone's running a query, we get a con.



84

00:16:50.120 --> 00:16:53.540

Technologic: the more… the more agents you're running, the more AI you're running, but… Yeah.



85

00:16:53.690 --> 00:17:02.459

Technologic: you know, the more we should make. And there's two dimensions to that on why this matters, right? Number one is that



86

00:17:02.620 --> 00:17:20.939

Technologic: as they onboard more users, we get more of that. And the second one is as they do more complex problems that require more turns, we get to cut that. And I think that's kind of the important bit, which is, like, even Notion's big hair-on-fire problem for us, like, the thing that they wanted us to do, which is, like, to backfills.



87

00:17:20.980 --> 00:17:24.539

Technologic: It's still only, like, a few, like, maybe 100K a year.



88

00:17:26.190 --> 00:17:34.549

Technologic: Right. Sometimes it doesn't… that's what I'm trying to say, like, yeah, like, I, I, like, I have an authority on, like, for, like, for example, the AnyScale workload that they run is only a few thousand a month.



89

00:17:34.950 --> 00:17:43.449

Technologic: Right, so even if, like, even if, like, we did that batch embedding pipeline for ingestion, it's not substantial enough. I see, yeah.



90

00:17:44.750 --> 00:17:46.419

Technologic: That makes sense.



91

00:17:47.120 --> 00:18:05.679

Technologic: So we need to be in the execution path, and we need to provide the end outcome. And at the end of the day, I just want to have one corner, like, I just want my… the product page just to be, like, three numbers. Yeah. That's it. Buy now, that's it. Yeah, exactly! So I don't think we need to… I don't think we necessarily need to be, like, the best, like.



92

00:18:05.960 --> 00:18:14.779

Technologic: component in terms of, like, trainable. I mean, we could end up potentially going down that path and building it, that's bespoke for our use case, but the idea is that, like, we're starting from these



93

00:18:14.970 --> 00:18:18.250

Technologic: data sources, and in the end, we're just giving really good results. Yeah.



94

00:18:18.570 --> 00:18:24.970

Technologic: Alright, if you're a systems company, like, you know, what kind of system are you building? I would argue here it's a search system, right?



95

00:18:27.020 --> 00:18:32.980

Technologic: One thing I'm curious about is, like, when we were working on DAFT, I think a lot of us



96

00:18:33.330 --> 00:18:39.850

Technologic: We knew the landscape, we knew the competitors, we knew AnyScale, we knew Ray, we knew Databricks, we knew Spark.



97

00:18:40.120 --> 00:18:44.520

Technologic: But for this one, we don't really know who the competitors or the other players are.



98

00:18:44.650 --> 00:18:45.400

Technologic: Bill.



99

00:18:46.120 --> 00:18:51.650

Technologic: And… Yeah, we don't. I mean, I think that the thing is, like, currently what we're seeing for…



100

00:18:52.190 --> 00:18:53.150

Technologic: There's, like…



101

00:18:54.850 --> 00:19:01.190

Technologic: I think that's true now for DAFT, right? But actually, when we started 3 years ago, we didn't know either.



102

00:19:01.190 --> 00:19:15.120

Technologic: Like, we're like, are we competitors with Polars? Are we competitors with Moden? Well, the repair itself, we were thinking for a long time that we were, and then we just said, no, fuck these guys.



103

00:19:15.170 --> 00:19:20.350

Technologic: And, like, I think when we realized that, like, they're not really, like, we're not even playing the same sport.



104

00:19:20.500 --> 00:19:27.810

Technologic: It didn't matter. Like, they were doing their thing, we're doing our thing. Yeah. And so I think in the beginning, there is a lot of muddiness, I think, that, like.



105

00:19:27.810 --> 00:19:44.189

Technologic: Because I think everything we're doing is very new, and I think it will be like that, and it will be uncertain, and I think they will navigate and pivot, and we will navigate and pivot, and that's just the natural order of things. Yeah, but I think it's built to be in a new market, because that opens up a lot of space. I do think that the agents



106

00:19:44.300 --> 00:20:03.120

Technologic: do open up, you know, a decent space and new categories of products. Yeah. Yeah, so I think it's good that we did the sprint, and actually saw first and put that. And now we can all say about aging tech search means, right? Before that, I mean, I wanted to… The other thing, I think, is, like, when we start to have more commercial conversation, those



107

00:20:03.660 --> 00:20:13.089

Technologic: potential customer, they will mention what they're using, and that they're considering, and the pinpoints are. So you know you are compared to them. That's actually…



108

00:20:13.330 --> 00:20:22.629

Technologic: your real competitor, rather than something in your imagination. One thing that is clear to me, actually, through the course of, like, the last two weeks, is that we're not some, like, context mumbo jumbo.



109

00:20:22.750 --> 00:20:41.519

Technologic: I feel like those companies do end up being like, we make your agents better because they get more context, like, something can be something, like, there's no way to measure it, like, no one's even adopting this stuff. So how do we get down to the hard system? Like, we know people need search systems, right? So we can find our category that way, rather than just following, I guess, yeah.



110

00:20:41.540 --> 00:20:44.089

Technologic: the buzzwords of, like, contacts and agents. Yeah.



111

00:20:46.470 --> 00:20:51.799

Technologic: What you said about… Oh, on the competition, like, how, like, glean, how… Yeah.



112

00:20:52.230 --> 00:20:57.989

Technologic: similar… I think it's… It's, like…



113

00:20:59.180 --> 00:21:04.369

Technologic: form factor-wise, it's, like, similar to what we want to do, to be honest, but I think the key difference is, like.



114

00:21:04.530 --> 00:21:20.249

Technologic: clean is, like, imagine you're, like, a very large company, and you have all these different, like, repositories of data, like your Slack, your eDrive, like, your HubSpot, like, all these different sources, and you want to provide your employees and your internal systems a way to search that data.



115

00:21:20.630 --> 00:21:25.350

Technologic: Now, the thing that we're doing is more like, imagine you're a company, like.



116

00:21:25.480 --> 00:21:37.019

Technologic: like, Notion, and what you want to do is provide a unified search experience, not only for, you know, Notion's, like, for, their Notion data, but for all of their sources that are connected to it.



117

00:21:37.020 --> 00:21:51.589

Technologic: And so the thing that we're doing is actually providing that search experience over third-party data. And so that would much more look like you log into a platform that you want to search over, and then you end up connecting your data sources to that platform, and then under the hood, it's actually us.



118

00:21:52.190 --> 00:22:02.310

Technologic: Yeah, I think the short version of that, actually, is just that Glean's customer is the person in the company searching, right? Our customer is very different. Our customer's business is trying to build an agent.



119

00:22:02.680 --> 00:22:18.820

Technologic: As the devil's advocate, why don't you, you know, why don't you want to be the one with the… capturing the eyeballs, right? Like, you're saying we are at the back and Notion has the eyeballs, like, why don't you want the eyeballs ourselves? Because that is the whole internal company search problem space, and…



120

00:22:18.820 --> 00:22:26.579

Technologic: Ethropic, Lean, and OpenAI are, like, currently bundling in there, and I think we can… So it's basically just, like, our… our approach to…



121

00:22:26.580 --> 00:22:50.609

Technologic: Correct. Yeah, because, like, I think right now, like, that's, like, everyone, it's completely. Every company we talk to wants to be the place you start and end the day. Can we be the arms dealer, and then go fight, you know? Like, no, that's exactly it, like, right now, OpenAI is doing all this knowledge stuff, so is Notion, so is Kuge, so is everyone else. I don't mind being an arm dealer. No, I don't wait to be the arms dealer. Like, why don't we help these people compete?



122

00:22:50.630 --> 00:22:51.460

Technologic: Yeah.



123

00:22:53.610 --> 00:23:15.080

Technologic: So we are the people who make sure that there's no duopoly. Glean is not trying to be infrastructure, right? They're not… They're trying to be a product. It's more like an application. Like, they're not trying to be fast, just play fast enough for humans to click on, not all. Yeah, so they are mostly catered for humans. So Glean's mostly for humans, but the whole thing is, like, they're selling to enterprises who, like.



124

00:23:15.210 --> 00:23:23.740

Technologic: just need a unified search, essentially, internal data, like, internal search. I know we do third-party… they very much do ingest third-party data.



125

00:23:24.740 --> 00:23:31.070

Technologic: Yes, but they don't… they ingest third-party from other platforms, but they don't ingest that company's third-party data.



126

00:23:31.650 --> 00:23:51.389

Technologic: Like, that company's customers have already data. There's also agent and consumers knowledge. Yeah, that's correct. So yeah, we're… we are connecting to the customers of our customers. Right. Yeah. But where you are correct is that the types of things that are built internally are very relevant for what we're trying to do. So you could think of it this way, we're making, like, we're making, like, a multi-tenant glean, essentially.



127

00:23:51.390 --> 00:24:00.690

Technologic: Or, like, the next glean could be building on top of AppSpeed. Yeah, yeah, exactly, exactly. And our bet is that there will be a lot more people trying to build these types of applications, right?



128

00:24:00.970 --> 00:24:11.519

Technologic: The other thing is, actually, Gling has use case for me as a marketer, but there's also something… what we're building is unlikely to have use case for me to use.



129

00:24:11.820 --> 00:24:18.859

Technologic: As a pure marketer person, yeah. But it could be for a marketing agent, you know? Sure, that's different, right? But, yeah.



130

00:24:18.930 --> 00:24:36.309

Technologic: Yeah. Because I do think that, like, as we see this, it's like, one thing I was playing with yesterday is, like, if you Google search for something like EXA, which is, like, mint for more agent, the results are very different. Yeah. Like, I think an example, you know, I think you told me, like, an example of, like, I want 100 halal recipes to have cucumbers, right? I was putting the query that in, right?



131

00:24:36.390 --> 00:24:42.700

Technologic: And, like, if I go on Google, it literally finds me listicles of, like, recipes that, like, aggregate 100 halal recipes.



132

00:24:42.920 --> 00:24:58.550

Technologic: Right? Versus, like, if I try to go to agendic surgery, it just gives me a link to the actual recipes. So, if I was a human… I mean, I am a human, but, like… But, like…



133

00:24:58.790 --> 00:25:00.359

Technologic: If, like…



134

00:25:01.200 --> 00:25:10.349

Technologic: as a human, what I'm looking for is, like, the listicle is fine, because it aggregates all the data for me, and that's a view I get. But for the agent, that's not just another layer of interaction.



135

00:25:12.790 --> 00:25:13.470

Technologic: Nope.



136

00:25:14.630 --> 00:25:30.810

Technologic: So anyway, it's like, it's not concrete, and that's why this Tiger team is going to do a lot of exploratory work, and I think that's the thing where it's like, I think on Monday we're going to propose, like, a team structure, but it's folks who want to lean into the chaos, right? Like, that's the… being honest, that's what it is.



137

00:25:31.620 --> 00:25:34.429

Technologic: Will we be the best at what we do, because…



138

00:25:35.000 --> 00:25:39.610

Technologic: The agents, because we're, like, optimizing between the interface between…



139

00:25:39.970 --> 00:25:42.910

Technologic: agents, like, we're the EXA for private data.



140

00:25:43.730 --> 00:25:48.810

Technologic: And we're, like, really great at the API layer, but we knew we had the UI for selling the access control.



141

00:25:48.960 --> 00:26:00.570

Technologic: like, in terms of, like, our customer is these agent filters, but in system optimization is the interface with the agents, not humans. I guess you're asking, what is, like, the secret sauce? Like, why we think we'll be good?



142

00:26:00.700 --> 00:26:04.780

Technologic: Yeah, well, I'm wondering if, you know, the…



143

00:26:05.250 --> 00:26:16.179

Technologic: Ability for us to go and test and optimize is, limited by human feedback, or, like, our ability to go and test with individual agents on private data?



144

00:26:16.670 --> 00:26:19.200

Technologic: Because I feel like it's a very different…



145

00:26:19.840 --> 00:26:24.570

Technologic: I don't think we even need agents to show value. Yes.



146

00:26:24.670 --> 00:26:31.830

Technologic: Okay. That won't be the ideal scenario, because, I mean, we all tried to rebalance and, like, wanted to kill ourselves, right?



147

00:26:31.940 --> 00:26:38.000

Technologic: I do think there's a world in which, and Sammy and I talk about this a lot, in which we can, like, find the hard metrics, like, if we can improve



148

00:26:38.060 --> 00:26:56.460

Technologic: at a certain amount of recall, search performance, then I can go to a customer and say, hey, like, you have a 30-second time budget for your product, you can do twice as many searches now, but your agent gets better. And, like, the other one is, like, we could literally just say, hey, here's the baseline where we just ingested all these stock conversations through VectorDB, here's our product, we have 20% better recall. Yeah.



149

00:26:56.480 --> 00:26:58.369

Technologic: Your… your product becomes…



150

00:26:58.370 --> 00:27:22.090

Technologic: that much better now. Yeah, and I think, Pauline and Sam saw this yesterday, when we were trying to pitch, oh, your agents get better, it's very fuzzy, right? They don't really understand, but if you can pitch the intermediate layer, they kind of just connect the dots and say, hey, like, if your search gets better, then your agents get better. What exactly does better mean? Yeah, exactly. Actually, like, even your search gets better, like, qualitatively, it's hard.



151

00:27:22.090 --> 00:27:36.299

Technologic: but if you tell me I get X number more searches, like, I can see how I could use that now. Exactly. Like, it could be something like, imagine you cut the latency and cost in half. Yeah. Both, right? The agent can run twice as many searches. Yeah, and like, if I get a rough half, I can…



152

00:27:36.600 --> 00:27:38.650

Technologic: There's 5 or more searches. Correct.



153

00:27:38.650 --> 00:27:57.660

Technologic: We asked Notion, like, how do you guys measure your search quality? And they literally said, vibes. We put two examples next to each other and look at… They don't even do the emails.



154

00:27:57.660 --> 00:28:08.599

Technologic: This is nice in the sense that there's always this tension with, like, even with DAPCA, I would say, like, there's tension between, like, doing stuff faster and charging for it, except for, like, you know, we charge for, like, double…



155

00:28:08.730 --> 00:28:13.520

Technologic: existed. Yeah. But then, if you say search is faster.



156

00:28:13.870 --> 00:28:20.050

Technologic: and then you do more searches, you charge to search, then you're aligned, right? Exactly.



157

00:28:21.110 --> 00:28:27.860

Technologic: AnySphere, the parent company of Cursor, posted this crazy thing on Twitter yesterday that they were…



158

00:28:28.050 --> 00:28:43.390

Technologic: doing this giant multi-agent thing, and committing, like, a thousand commits a minute, or something like that, and thinking, like, you know… Yeah, so there is a future… there's a couple of threads we can talk about off this convo, but it's a couple of threads and trends that I think we can write on.



159

00:28:43.440 --> 00:28:52.549

Technologic: one that I think this points to is this idea of, like, long-running agents, right? If you have a long-running agent, the more searches it can do, the faster it can do as well, you know? So there's a bunch of things.



160

00:28:52.660 --> 00:29:10.590

Technologic: Actually, one angle that I think is very nice is that, you know how almost every agent out there doesn't use Grab? Use Rip Grab? It's their web search, they say rip web search, right? Yeah. Or… I think I want to give people, everybody else, maybe, also a chance, if anybody has questions around, like.



161

00:29:10.700 --> 00:29:20.929

Technologic: how did we make the decisions on DAP Cloud, or, like, anything, right? Like, I know a couple of you have kind of brought it up in our 101, so I think this is… because if you have a question, others might also have the same question, so…



162

00:29:26.950 --> 00:29:31.059

Technologic: Yeah, I guess especially maybe Corey and Trino on the call.



163

00:29:35.260 --> 00:29:44.989

cory grinstead: I guess one question I had about, like, DaptCloud was, like, At least from…



164

00:29:45.750 --> 00:29:51.870

cory grinstead: You know, my perspective, like, seeing, like, something optimized, like,



165

00:29:53.370 --> 00:30:00.409

cory grinstead: batch inference service that was kind of, like, well optimized for that. Seemed like something that would have been…



166

00:30:04.230 --> 00:30:11.230

cory grinstead: Would have been, like, profitable, or would have been, like, worth, we're chasing… And I guess, like…



167

00:30:11.730 --> 00:30:18.239

cory grinstead: you know, I haven't been part of any of those calls, so maybe we could just, like, talk a little bit more about, like, why that…



168

00:30:18.490 --> 00:30:22.579

cory grinstead: Why that didn't work out, and, like, the whole, like, batch inference side of…



169

00:30:22.830 --> 00:30:25.450

cory grinstead: Angle didn't really, pan out.



170

00:30:26.360 --> 00:30:31.129

Technologic: I think the batch and Prince one was actually a direction we did… me and Jay did explore, actually.



171

00:30:31.390 --> 00:30:37.020

Technologic: That was one of the ideas that we had as well. But the thing is, like, we're coming out of our first principles.



172

00:30:37.130 --> 00:30:40.490

Technologic: At what is actually a good interface for badge inference.



173

00:30:40.860 --> 00:30:47.490

Technologic: It… what we kind of found is the way most people think about batch inference, it's kind of this unified thing across both offline and online.



174

00:30:47.910 --> 00:30:53.399

Technologic: like, whether the batch is for an offline job versus an online job, it doesn't really make a difference, you just throw it into a queue.



175

00:30:54.050 --> 00:31:08.299

Technologic: And so, given that the form factor that, like, might be the simplest form factor for batch inference, what we thought about isn't something like a data frame or, like, DAFCloud. It's actually more something like a web request.



176

00:31:08.730 --> 00:31:10.210

Technologic: You know? Or like a queue.



177

00:31:10.470 --> 00:31:21.669

Technologic: like, containers, you know? Which is why we see, like, you know, things like the run pods and the modals and, like, all of that, doing more of those workloads. And the other part we saw is this, which is…



178

00:31:23.040 --> 00:31:36.560

Technologic: if you look at those companies that are doing well for batch imprints, it's all on models that are not LLMs. Yeah. Because for LLMs, you typically, you know, it's token in, token out, it's fairly… it's fairly simplified interfaces, and that's where you see, like, the,



179

00:31:36.910 --> 00:31:42.160

Technologic: things like the fireworks and, like, the base tens and all of that. We're there as it's just…



180

00:31:42.680 --> 00:31:56.769

Technologic: making inference really, really fast, yeah. And so there's kind of those two things where either you go pretty low level as an infra product, or go very high level as an inference product. And in the middle, there's not much room, is what we saw.



181

00:31:57.090 --> 00:32:16.589

Technologic: That's kind of where Model operates, in that middle. Yeah, so I think what happened is, like, even with, like, from what I see with the ray data workloads, is that actually the batch inference runs as serving in VLM, and the ray data doesn't even run the GPU inference anymore. That's what we're seeing as well, I see. That's what we did, honestly. That's what we did in the end as well.



182

00:32:18.000 --> 00:32:21.780

cory grinstead: So it's just that there's already, good enough alternatives out there.



183

00:32:23.230 --> 00:32:30.060

Technologic: But yeah, I mean, it's a good thought, it's a good thought. It's a good thought. It's one thing that we considered, but the interface would be very different, and I think…



184

00:32:30.190 --> 00:32:45.759

Technologic: I don't think it's conclusive yet, but we were unconvinced that it was, like, a big, big market opportunity. No. Yeah, interface would be, like, fire off the thing and get, like, a task ID, essentially. Yeah. The data frame is just not flexible enough for all, so…



185

00:32:46.200 --> 00:33:01.280

Technologic: Yeah. Yeah, and I think in the opportunity space, or, like, how big the TAM is, like, batch inference will still sit in your write path rather than your read path, and I think you'll see, like, it's a huge difference between the amount of traffic a read path gets versus the right path.



186

00:33:01.340 --> 00:33:10.469

Technologic: So, the TAM is more of a pursuant as well. There is a world in which, like… actually, we talked about this with one of our board members, in which batch inference becomes part of the VPath.



187

00:33:10.540 --> 00:33:23.970

Technologic: Where if you have these long-running agents, and they're comfortable waiting for a long time, you can imagine that they'd be comfortable, like, running on batch request. That was one of the hackathon prompts that we had, was the async imprints machine.



188

00:33:23.990 --> 00:33:41.110

Technologic: And the idea was that, like, imagine you have these, like… imagine you have, like, a… like, a agent that's, like, maybe not as high priority, like, or as urgent. It can run in the background and actually, like, investigate things, look into things, and it can enqueue a request, and while it's waiting, it can just send.



189

00:33:41.250 --> 00:33:54.349

Technologic: and then get back the result when the inference is the cheapest, and then continue forward. And so this idea of, like, not necessarily batch inference, like, I throw a bunch of things into, like, a queue and, like, wait for all of it to complete, that's just more of an idea of, like, agents can, like, do these async calls.



190

00:33:54.390 --> 00:34:02.159

Technologic: And then they get reawoken when they're there. This was one of the paths of these long-running async agents, was one of the hackathon problems we had as well.



191

00:34:05.680 --> 00:34:09.750

Technologic: There is some, like… we did see some signal there as well.



192

00:34:12.020 --> 00:34:15.350

Technologic: But once again, it's not the form factor of… that won't go.



193

00:34:19.320 --> 00:34:21.579

Technologic: Yeah, good question, Corey. Thank you.



194

00:34:25.620 --> 00:34:27.069

Technologic: Shane knew anything from you?



195

00:34:28.980 --> 00:34:33.969

Sri L: I know! Was it this… yeah, this Wednesday?



196

00:34:34.909 --> 00:34:43.440

Sri L: after… we showed… kind of the final results. We… Kind of mentioned that to…



197

00:34:44.100 --> 00:34:47.879

Sri L: One aspect that kind of made the CS agent a little bit hard to



198

00:34:48.150 --> 00:34:58.230

Sri L: to, work through was, or evaluate, was the idea that we weren't really sure if we had interesting data. Like, we weren't sure if our



199

00:34:58.320 --> 00:35:08.979

Sri L: like, the amount of the volume or the complexity of our internal data set from our Notion, our Slack, our GitHub, was, like, interesting enough to



200

00:35:09.090 --> 00:35:14.460

Sri L: really determine if librarian would do a better job, but for the Tiger team.



201

00:35:14.680 --> 00:35:18.349

Sri L: Will they be working with a design partner?



202

00:35:18.960 --> 00:35:26.909

Sri L: Have a separate set of data that we can use to evaluate, or will we continue to use our own internal data?



203

00:35:27.380 --> 00:35:31.629

Technologic: Yeah, so I think the first part of it is, I think, for getting started.



204

00:35:31.920 --> 00:35:34.149

Technologic: and building something, I think…



205

00:35:34.760 --> 00:35:46.689

Technologic: we… we're not going to be using end-agent performance anymore as a metric. It will first probably be starting to walk, which is, like, how do we… how do we get relevant search working first? And now it'll be on a corpus of data that we can set up.



206

00:35:46.690 --> 00:35:55.820

Technologic: that's not our internal company data, but, like, a large enough purpose where it's actually interesting to do search. And we should be able to compare against other systems. So, for example, the way I think about it is that there's…



207

00:35:56.170 --> 00:36:14.029

Technologic: things like Elastic and BM25 already, we should be able to compare against that for an agent right away, and compare, like, the relevant quality, and try to compose that into metric. In parallel, Jay and I are just lining up as many calls as we can to find a design partner for this. We have a few prospects already lined up, but the idea then is



208

00:36:14.110 --> 00:36:24.149

Technologic: Yeah, deploying prod, right? We give it to them, and we let them tell us, like, hey, this is… I don't like this result, I like this result, and we can use that feedback to then come up with our own metrics for search that makes sense. Yeah.



209

00:36:24.560 --> 00:36:30.189

Technologic: Is it also fair to say the Tiger team will probably focus on quality first, more than performance?



210

00:36:31.470 --> 00:36:34.599

Technologic: Because performance, you really need, like, a big, complex data set.



211

00:36:34.900 --> 00:36:49.219

Technologic: In order to… Yeah, you can always have a fast query by returning whatever, right? Well, you can always have a fast query by having 100 bugs. I actually think it's… it's actually more, like, best results under a budget. So not, like, for example, in the notes and thing, the thing that, like.



212

00:36:49.480 --> 00:37:01.789

Technologic: the number one metric they said, the thing… we asked them what's the most important thing, they're like, performance, and then our demo took 30 seconds to run. We sampled all that out, right? So, I think it is… it needs to be fast enough.



213

00:37:02.860 --> 00:37:09.640

Technologic: But I think that is how people think about it. Yeah. They don't think about it as fast as possible. They think about it as, I have a budget. Yeah.



214

00:37:10.010 --> 00:37:16.589

Technologic: This budget was set for, like, P99, so… It's… the budget is… the metric that they said exactly was…



215

00:37:16.800 --> 00:37:19.930

Technologic: 100 miles, I can beat that day. I see, yeah.



216

00:37:20.600 --> 00:37:24.620

Technologic: I think it's just they have, like, a product quality bar. Yeah. Right. Yeah.



217

00:37:24.810 --> 00:37:41.950

Technologic: And for them, they have all these other metrics after us, right? They have their own rankers, their own rankers, their own back, and their own thing. So we can actually go to them saying, hey, this is our bounded P90. That lets them have that mental contract with us. Yeah. And that lets them say, okay, this is how it fits my stock. Yeah.



218

00:37:42.280 --> 00:37:43.400

Technologic: Yep, yep, yep.



219

00:37:46.250 --> 00:37:47.370

Sri L: Okay, makes sense.



220

00:37:47.590 --> 00:37:48.150

Technologic: Nope.



221

00:37:50.410 --> 00:37:54.670

Technologic: But yeah, once again, we're leaning into the chaos, so, we'll figure it out.



222

00:37:56.510 --> 00:37:57.300

Technologic: Chris?



223

00:37:58.060 --> 00:38:05.020

Technologic: Yeah, I guess you were out for a bit, so this is kind of crazy for you. Welcome back to the camps!



224

00:38:06.920 --> 00:38:14.820

Technologic: Yeah, I'm just… Catching up on a lot of what happens last week was, interesting, and…



225

00:38:16.390 --> 00:38:21.159

Technologic: Yeah, I'm just kind of curious where we sort of navigate to and land.



226

00:38:21.310 --> 00:38:25.910

Technologic: Yeah. Yeah, I will say that there is a bedrock here, we're just staffed, you know,



227

00:38:26.010 --> 00:38:34.120

Technologic: there are some very real things that we need to deliver on that, and I think there's been a couple of things we've… like, there was kind of a winter break and two, you know, hackathon weeks.



228

00:38:34.300 --> 00:38:40.599

Technologic: So, there are some very common things that we want to deliver on it, and people relying on us to deliver that.



229

00:38:41.410 --> 00:38:44.760

Technologic: the data for open source. I know, like, Apple…



230

00:38:45.600 --> 00:38:53.550

Technologic: the support, or something like that? Yes. Are you… are you… are we open to, like, more support things through DAF, or is that… or…



231

00:38:54.320 --> 00:39:00.019

Technologic: I think we should talk. I would be open, depending on our capacity, and depending on the requirements.



232

00:39:00.730 --> 00:39:14.800

Technologic: Apple actually, surprisingly, the requirements aren't that heavy, just yet, maybe? Just, yeah. I think that they… I think they're ramping up, yeah. They're ramping up. I think they're getting their, like, gear, because I think they're doing a lot of buying now, they're ramping up. I think the key thing is, like.



233

00:39:15.100 --> 00:39:17.680

Technologic: It's, it's more about, like, if…



234

00:39:18.700 --> 00:39:33.629

Technologic: what they want is compatible with the vision of what we want. Yeah, that's kind of how I see it, because, like, I was in the memo, we have, like, we have a lot of runway, right? We have the room to explore. So it's not like we need the money, but I think we need really quality, like, high-quality design, like, people to work with.



235

00:39:33.990 --> 00:39:46.879

Technologic: I mean, I think of these as usually, like, does it align with the managed product I'm building? And can I use this as, like, a foot in the door to actually eventually sell the product in the future? If the answer to that is no, then probably no.



236

00:39:46.890 --> 00:39:54.610

Technologic: So, for example, Apple, like, we had an out-of-band meeting with Apple, like, a week ago, and they were like, hey, we're actually starting to build data agents.



237

00:39:54.910 --> 00:40:06.729

Technologic: And the first, the context thing maybe wasn't the right thing, but actually providing the super-fast, like, search for them to build their agents could be extremely relevant to them. And so that, even though we're working on the open source side, it opens the door.



238

00:40:06.840 --> 00:40:19.289

Technologic: to work with them with other teams as well. Because their whole thing inside right now is like, hey, how do we actually build more agents for Apple customers within, like, iOS and all that, now that they have Gemini? That was kind of the big blocker for them internally.



239

00:40:20.270 --> 00:40:32.499

Technologic: like, a TLDR for direct people to do it? No. Not just for the rev… there's never a lot of revenue. The revenue's not, like, substantial for us, right? And we want to make platform revenue, so…



240

00:40:35.200 --> 00:40:37.720

Technologic: Any books, error, do you have anything?



241

00:40:38.290 --> 00:40:40.029

Technologic: You know, I think,



242

00:40:44.450 --> 00:40:57.979

Technologic: this team is, like, poised to do really well, focus on, like, a search problem. This is… this team is, like, so strong at systems engineering and making things wicked fast and performing. I think that's, like, really exciting. I feel like.



243

00:40:58.190 --> 00:41:03.560

Technologic: Once we have these, these metrics, That's… gonna help…



244

00:41:03.840 --> 00:41:07.300

Technologic: I think make it… things a lot more concrete,



245

00:41:07.760 --> 00:41:12.050

Technologic: You know, and maybe the earlier we can get the data, the better, but,



246

00:41:12.320 --> 00:41:18.340

Technologic: you know, I'm honestly just, like, curious with, like, your background, like, Sammy, like, what you think.



247

00:41:18.490 --> 00:41:26.540

Technologic: like, kind of an anchor is on your vision for what search really means, at least to start out with, if you've got, like.



248

00:41:27.970 --> 00:41:28.780

Technologic: Yeah.



249

00:41:29.130 --> 00:41:42.529

Technologic: I mean, the way… the way I see it is that, like, I think the thing that resonates with everyone that I've talked to so far is when I say, hey, you don't… you shouldn't search… like, the way you search for Slack is different than the way you search for a document. And I think that resonates with almost everyone I talk to.



250

00:41:42.970 --> 00:41:43.790

Technologic: Right.



251

00:41:43.910 --> 00:41:46.499

Technologic: And I do think now that, like.



252

00:41:49.380 --> 00:41:56.970

Technologic: I do think now that, like, folks are trying to, like, deploy more agents on the things, it's more of a need to actually, like, make this data a lot more…



253

00:41:57.460 --> 00:41:58.970

Technologic: discoverable.



254

00:41:59.210 --> 00:42:06.770

Technologic: searchable and, like, just relevant, right? Because these downstream things are very, very expensive. And so the way I see it is that, like.



255

00:42:07.120 --> 00:42:14.489

Technologic: That's kind of how I see it, to, like, unlock all these modalities to these downstream folks that are just floating in usage. I don't know what that exactly looks like in the system yet.



256

00:42:14.940 --> 00:42:22.050

Technologic: I don't know exactly what that looks like in search results yet. Yeah. Right? But I think that's what I want to find out. That's the point of the Tiger team.



257

00:42:22.490 --> 00:42:23.210

Technologic: Right.



258

00:42:25.080 --> 00:42:26.929

Technologic: I guess, like, the modality.



259

00:42:27.690 --> 00:42:35.549

Technologic: Yeah, like, what does it mean to search for videos? What does it mean to search for images? What does it mean to search for documents? Yeah, and the Patreon kind of data point I have here was that



260

00:42:35.550 --> 00:42:51.949

Technologic: Thomas was like, yeah, most of our videos are just, like, someone sitting there talking to a screen. It's a very different type of search than my YouTube, but, like, a whole bunch of other stuff. Yeah, so if you type in for, like, every video Patreon is this person sitting in chat. If you use, like, flip embedded, let's use it. Yeah. Exactly. Right?



261

00:42:52.740 --> 00:42:53.740

Technologic: Transportation.



262

00:42:53.900 --> 00:43:05.640

Technologic: I would say, as, so we don't just glaze ourselves too much, I do think we are very strong at systems and performance. I would say, in terms of, like, search itself, that's the thing we need to, like.



263

00:43:05.760 --> 00:43:18.109

Technologic: there's a thing where the ambiguity in the research might come in, because what does it mean to do a good search? I don't think we necessarily have the expertise for that. I don't think so, yeah, either, right? And I think that's kind of the thing where, like.



264

00:43:18.120 --> 00:43:34.859

Technologic: hey, we're good at reading systems papers and coming up to speed, right? Yeah, yeah, yeah. Like, Yum25 was invented in the 60s. Yeah. Yeah. It does feel a lot closer that, like, you said about taste. I have no taste for what's a good agent. I should develop taste for what's good search. Yeah.



265

00:43:34.990 --> 00:43:57.939

Technologic: what's a well-optimized search performance? Yeah. Yeah, like, you had that argument the other day, I was talking to Sam, I was like, hey, at the end of the day, we have kind of a diverse team, and, like, we can kind of build new systems, and, like, Sam Challenge was like, no, we don't have a diverse team. We actually have a team that's good in systems. Yeah, that's fair. I actually would like to… that, like, I was the one that, like, told Sam, hey, like, let's do agents, you know, because I think I'm on the spectrum, less systems, you know, most people.



266

00:43:58.310 --> 00:44:00.189

Technologic: Right, but, like, at the end of the day.



267

00:44:00.300 --> 00:44:18.460

Technologic: thinking about… I know what you're gonna say, my stance… I even say that to you, I was like, this team is good as a certain team. Yes, yes. But, like, yeah, at the end of the day, I think we just, like, follow our DNA, and what calls us, and, you know, and where we think we can kind of make the most difference, and yeah, it's systems, data, right, databases.



268

00:44:18.550 --> 00:44:21.850

Technologic: Yeah, we go back to that, and I think there is a world in which that



269

00:44:22.030 --> 00:44:27.390

Technologic: It's super, super important, really, really impactful. Yeah, yeah.



270

00:44:27.550 --> 00:44:35.479

Technologic: Yeah, I mean, I… here's the thing, like, me and Dave went back and forth on this, which was like, hey, should we just go, like, Latfield as possible?



271

00:44:36.460 --> 00:44:52.009

Technologic: But, I don't know, I think I was like a lot of you guys, too, which is like… I was like, okay, this is so unknown for me, and, like, so, like, different, that I'm like, the prospect of it is exciting. Yeah. But then, as you said, you went to Gastown, you never want to go back.



272

00:44:52.400 --> 00:44:59.949

Technologic: It's interesting where it's like, I actually really like working with these AI systems. It's really fascinating.



273

00:45:00.740 --> 00:45:02.640

Technologic: Do I want to be the person writing the prompts?



274

00:45:02.860 --> 00:45:16.049

Technologic: Like, not really, not really, right? That's kind of how we see it now, which is like, okay, how do we leverage all of our skills that we accumulated over our careers, but in a way that we service the modern market? Yeah, yeah, yeah.



275

00:45:16.550 --> 00:45:21.160

Technologic: Yeah, very much want to, like, build these agent capabilities, not, like.



276

00:45:21.360 --> 00:45:29.410

Technologic: build the agents, or use… maybe use the agents, but, like… I think using them is fine, and, like, testing them is fine. Like, all the search we build, like.



277

00:45:29.440 --> 00:45:33.539

Technologic: Our first thing for dog foodie is we should probably just rip out, like.



278

00:45:33.560 --> 00:45:38.110

Technologic: maybe the search that Cursor Cloudco does by itself and use our search. Yeah, yeah, yeah.



279

00:45:38.120 --> 00:45:53.800

Technologic: Right? Honestly, like, this could even be, like, a way you can enter the stack for, like, Cloud Code, or, like, all these, like, regular, like, mainstream agents, not just, like, all the niche agent builders, right? Like, everyone's gonna need some fast search of these documents. Yeah. Right?



280

00:45:54.300 --> 00:46:02.080

Technologic: like, another… there's a lot of segments here, too, like, I don't know, thinking about it, like, if you go to… there's a lot of these forward-deployed engineers. Yeah.



281

00:46:02.450 --> 00:46:16.170

Technologic: what if we can go to the four deployed engineers who are doing integrations for their customers, and we give them this product? Yeah. Now they have cloud code that can access all of their customer data, right, in, like, a unified way. So now they can, like, be super effective being in FTE. Right.



282

00:46:16.350 --> 00:46:22.889

Technologic: And so there's a lot of these segments I think we can light ourselves into. Yeah. Right? And I think the market is, like, on top right now. Yeah.



283

00:46:23.320 --> 00:46:38.570

Technologic: Yeah. Also, like, I think, let's not assume that we know 100% of what we're gonna build right now, actually. We have, like, a month, we will kind of… we might change, so it might be, like, different form after, right? Like, yeah. I think the fear part of this is we need to be on token path.



284

00:46:38.940 --> 00:46:41.120

Technologic: And,



285

00:46:41.400 --> 00:46:59.660

Technologic: Yeah, and I guess that's the most important thing. It could be actually interesting, at the end of the day, we decided to sell to a forward deployed engineer instead of the builder themselves. No, exactly. That's one of the aspects I've been thinking about, like, like, half of the engineers being hired now are FDEs. Yeah. Right? And so, like, if we sell to them and we make them FDE twice as fast… Yeah.



286

00:46:59.840 --> 00:47:03.820

Technologic: then the FBEs start using it by default, then…



287

00:47:03.860 --> 00:47:21.180

Technologic: that becomes a product defect. I think there's a lot of avenues to explore, but, like, yeah, like, that's part of what, you know, Jay and I are gonna have. But to be clear, like, on the Tiger team, like, that's… I will be on the Tiger team. Yeah. Like, I'll be working with everyone on there, yeah.



288

00:47:23.050 --> 00:47:28.099

Technologic: Oh, we're gonna do awards? Oh, yeah. Maybe two more minutes, like, any call in.



289

00:47:28.410 --> 00:47:33.719

Technologic: Any questions? I know you've been kind of, like, probably being exposed to this a little bit longer than most other folks.



290

00:47:34.020 --> 00:47:40.839

Technologic: One week longer. Like, one week longer. Give us the, give us the recap, the end of… Huh? Recap? Yeah.



291

00:47:40.970 --> 00:47:47.879

Technologic: We kept, day one, Sammy and Jake came back, I saw a meeting on my calendar called Secret Project.



292

00:47:48.490 --> 00:47:58.409

Technologic: Forget everything you know about that. So, like, I mean, I think over time, I think, like.



293

00:47:59.810 --> 00:48:05.350

Technologic: I've seen that, like, I personally have approached this as an agent problem.



294

00:48:05.600 --> 00:48:17.130

Technologic: And that being said, like, you know, I approach things like evals, like, I need very hard evals, because that's how you evaluate agents, that's how you evaluate how agents are good. I can definitively say.



295

00:48:17.350 --> 00:48:24.900

Technologic: That's… that's not something I want to do. I'd much rather do systems, so we can approach this with a systems perspective.



296

00:48:25.160 --> 00:48:28.469

Technologic: That would, that would, that would be great, yeah. No? Yeah.



297

00:48:29.380 --> 00:48:41.420

Technologic: Yeah, I want to commend you on that. You leaned in fully, like, the email AI engineer about. I mean, you were manually, right, writing the… I guess you're manually writing.



298

00:48:41.740 --> 00:48:43.559

Technologic: Especially outputs. Yeah.



299

00:48:43.670 --> 00:48:44.330

Technologic: Yeah.



300

00:48:45.400 --> 00:48:52.530

Technologic: Yeah. No, I think it's true. I think… but do you think, I guess all of you guys, be honest, like, do you think this was worthwhile to do? Yeah.



301

00:48:53.600 --> 00:48:55.190

Technologic: Yes. Yeah.



302

00:48:56.510 --> 00:49:00.750

Technologic: I think one thing that was, like, very interesting also was just, like.



303

00:49:00.930 --> 00:49:07.700

Technologic: the… while we were doing this, I think the pace of everyone else in the industry was also just, like… Yeah.



304

00:49:07.840 --> 00:49:23.670

Technologic: like, we were moving in line, pretty much in line with them, like, new articles related to what we were doing came out every single day, from OpenAI, from other startups, from VCH, like, talking about very adjacent things to what they're doing. So I do think there is, like.



305

00:49:24.700 --> 00:49:33.540

Technologic: There's clearly there's a market for this, clearly there's a problem, but, like, who's… what's the solution? Who are the people who are going to take the… take the shares? I don't… I don't know yet.



306

00:49:33.880 --> 00:49:34.890

Technologic: No? Yeah.



307

00:49:35.750 --> 00:49:39.119

Technologic: It's a… it's a, it's a non-anonymous.



308

00:49:41.250 --> 00:49:43.920

Technologic: Yep.



309

00:49:45.570 --> 00:49:51.959

Technologic: Okay, cool. Sam, anything for you, Steffi? I said too much already.



310

00:49:52.290 --> 00:49:55.710

Technologic: I guess they go to what Colin was saying.



311

00:49:56.310 --> 00:49:58.529

Technologic: I'm glad we did the exploration.



312

00:49:59.870 --> 00:50:05.259

Technologic: And it feels like… There are so many people tackling the agent side of things.



313

00:50:05.790 --> 00:50:21.549

Technologic: Like, even if we were really good at that, it would have… we would have struggled to stand out. Like, systems is hard. Yeah. Yeah. Not many people are good at that. Systems are gonna get harder with all these people using agents and not learning. Yeah, and like, the other advantage we have is that, like.



314

00:50:22.340 --> 00:50:35.389

Technologic: Have you guys met, like, the average engineer now working in this space? Oh, man. It's not great. Like, we have a huge edge. Generally, average engineers are, like, going down. Like, I've asked them, like, what happens when you go to google.com, like.



315

00:50:35.840 --> 00:50:54.979

Technologic: to a data center? It's like, more details, let me know. But I think, Sam, you're exactly right, which is, like, I think everyone, like, is going on the agent path, because it is, like, the shiny thing right now. It is the thing that has the most articles out there. Like, going toward fundamentals and building to serve all these folks.



316

00:50:55.520 --> 00:51:01.640

Technologic: I think that's inevitably where we will be most successful, and also, like, it's the higher, like, revenue for us.



317

00:51:03.340 --> 00:51:16.120

Technologic: Okay, cool. We have 5 minutes left, so I wanted to, talk about the hackathon winners. So, what we decided to do, or, you know, Varun, Varun actually thought of this great idea, which is, we kind of, like.



318

00:51:16.580 --> 00:51:39.560

Technologic: switched up on you halfway through, so we decided to… Sorry for the being switched. Yeah. Now there's a benefit to it. Yeah. There's a benefit to it. So, you know, like, it's like when you play poker, and you know how, like, you have one, you know, sometimes you have, like, one board, and you can switch to two boards, and there's two, you know, one big pot. Oh, side pod. We decided to do it. So we ended up doing a week one and a week two.



319

00:51:41.850 --> 00:51:56.089

Technologic: like, as I was saying earlier, like, I felt like for week one, one thing I really respected is just how much, like, Colin and Trinu and, like, YK leaned into, like, actually looking at the data, writing the heaths, like, really sinking their deep into it.



320

00:51:56.160 --> 00:52:03.309

Technologic: Like, I think that was really impressive, and I think it was very much, like, out of, the comfort zone, too.



321

00:52:03.960 --> 00:52:15.169

Technologic: Right? I think oftentimes we, like, lean to, like, what is comfortable, versus I felt like this team really leaned into what was uncomfortable. I could see, you know, viscerally uncomfortable.



322

00:52:15.740 --> 00:52:32.799

Technologic: But I think that was the point, which is I wanted, like, I think it was important for us to be uncomfortable, to kind of, like, push the boundaries of what we can do, and learn maybe what we should not do. Yeah, I guess you want to add to that, Maroon, for you, Preach? Yeah, no, I just want to say, like, yeah, this team, so…



323

00:52:32.970 --> 00:52:37.629

Technologic: The team's the winner, right? Oh, yeah, yeah, Team 1.



324

00:52:38.470 --> 00:52:56.440

Technologic: Yeah, I think the team explored kind of different areas, kind of the three started different ways, did different evals, kind of, I think we learned a lot about evals, which I think we were able to, kind of, take those learnings into the second week, and that was kind of one of the factors, and talked about, like, how what the learning depth was.



325

00:52:56.440 --> 00:53:09.250

Technologic: overall, I think of all the things we did, I think this clicked the most as well, like, this might or might not be what we continue, but it definitely kind of clicked. We had a bunch of interesting results to kind of see when we talk about Windows, or when we kind of, like.



326

00:53:09.330 --> 00:53:26.200

Technologic: put in, kind of, we had five different kind of evals we did. So I think, overall, this team kind of delivered interesting results. We kind of learned a lot from it. It had a click factor, so I think, it was the winner. I think a lot of other teams did a ton as well, but I think this team stood out. Yeah, yeah.



327

00:53:28.540 --> 00:53:30.840

Technologic: You know, speech.



328

00:53:31.140 --> 00:53:32.700

Technologic: Huh? See?



329

00:53:33.200 --> 00:53:52.929

Technologic: I'm taking Srinu to Korean barbecue. Hold on, there's a second part to it. Srinu is taking us to this, vegan restaurant called The 12th Month. It's, like, a really good vegan restaurant, but it's not a bit fancy, so that's what Shino's taking us.



330

00:53:52.930 --> 00:54:00.560

Sri L: Yeah, my goal in life is to get Colin to say that he generally liked a meal that was completely, like, vegan or vegetarian.



331

00:54:00.560 --> 00:54:08.579

Technologic: I took Colin to, like, an amazing dosa place, and he was like, needed more protein.



332

00:54:11.540 --> 00:54:13.310

Sri L: how can I beat that? Oh my… ugh.



333

00:54:13.620 --> 00:54:16.870

Technologic: All right, no, no, no, 12 months is good, I have faith.



334

00:54:16.870 --> 00:54:18.350

Sri L: Okay, I believe in your room.



335

00:54:21.580 --> 00:54:22.520

Technologic: Okay.



336

00:54:22.640 --> 00:54:29.970

Technologic: And then I think for weeks… so, you know, at the end of the first week, we kind of, like, consolidated the four projects into, like, one engineering sprint with, like, different components.



337

00:54:30.200 --> 00:54:35.330

Technologic: And I think the call-out here I wanted to give out was for honoring Sam.



338

00:54:35.640 --> 00:54:49.349

Technologic: Like, I think I really respected how you, like, stepped up to kind of, like, PM facilitate the whole thing, and I… for Connor, I really respected how he, like, kind of took it out of product perspective and kind of really thought the prompt… thought about the problem, like, very deeply.



339

00:54:49.590 --> 00:54:54.579

Technologic: And so I think for that, like, yeah, week two winners are honoring them. Yeah.



340

00:54:56.950 --> 00:55:17.589

Technologic: Hey, do you want to add to that? No, I think, like, yeah, for both of… I think you, I think, Sam, you kind of stood up. I kind of took this end-to-end role, which is kind of awesome to kind of see, kind of put all the different pieces together. And I think Connor kind of, like, continued from what he started, right? Like, he started at, like.



341

00:55:17.610 --> 00:55:38.949

Technologic: looping thing, and kind of building it to a point where we were like, hey, this is, like, even, like, close to a demoable thing, or… No, I did demo it. Okay, so all the things that we did, that was kind of the demo thing, right? So I think that's pretty awesome. It matches kind of how he's not here, but it kind of matches how Connor works, like, kind of, like, you give him something, get him frustrated about something, you just fulfill it.



342

00:55:38.950 --> 00:55:42.699

Technologic: That kind of… Yeah, it seems on your end.



343

00:55:43.010 --> 00:55:47.480

Technologic: I would like to thank the Academy.



344

00:55:48.070 --> 00:55:50.870

Technologic: Yeah.



345

00:55:51.160 --> 00:55:57.939

Technologic: Okay, so I guess, like, for the prize, like, I guess there's multiple ways. One is, like, I can just… we can just pay them out, or we can put into a pool for you guys to do something with it.



346

00:55:59.470 --> 00:56:05.079

Technologic: So what is this, 4500 or 5K total? 5k and 5K total. Sorry, a thousand bucks each.



347

00:56:06.420 --> 00:56:21.020

Technologic: You guys can decide. You guys can decide. Wait, I didn't understand the choice. What is the question? Oh, I can, like, we can just… I can just give it to you guys in payroll, right? You need to pay tax. You need to pay taxes, or I can just give you guys a bull.



348

00:56:21.110 --> 00:56:25.030

Technologic: Go do something, 5 of you go do something worth 5K.



349

00:56:25.030 --> 00:56:46.710

Technologic: As long as we don't end up on the information, like, don't, you know, I think that's fine. Till the time you do not go to places that a company should not be sponsored by. In the beginning of the company, I remember our accountant came to me and was like.



350

00:56:46.710 --> 00:56:56.559

Technologic: Sammy, how do I categorize all these, like, temple expenses? Right? I'm like, what? And then I looked at the expenses, and then Jay wouldn't go buy a sandwich in the cafe inside of him.



351

00:56:56.880 --> 00:57:12.869

Technologic: Go drink lunch and get, like, a little burrito there. We have literally religious service for every employee. The pizza is a nightclub. I know, I know. We have all these, like, nightclub expenses. Okay, that makes more sense.



352

00:57:13.000 --> 00:57:24.020

Technologic: He's working fine. Yeah. No, but it was at, like, 11am, so, like, I don't know what… Yep.



353

00:57:24.070 --> 00:57:33.769

Technologic: Okay. All right. But yeah, thanks, everyone. I think everybody kind of, like, had, like, tough, interesting stuff. I know, like, Team Zero built the intro for it, like, Desmond Connor did kind of, because…



354

00:57:33.770 --> 00:57:46.100

Technologic: got us to a point where we realized that, hey, we should not kind of do, like, an agent-based sync product, like, multiple people are kind of already doing it, right? Then Corey and you guys kind of, like, did that experiment, Everett, like, to kind of figure out how we can



355

00:57:46.100 --> 00:57:52.740

Technologic: Have the clon agent, like, follow prompts and go out of its way and, like, do what you kind of wanted, right?



356

00:57:52.740 --> 00:58:10.319

Technologic: Sam Rohit, you guys kind of did the R&M exploration, decided it's not kind of worth going down. No, but I think there's still good aspirations, right? I think those are still, like, data points we, like, learned, because one other thing was kind of learning, right? So, thanks to everyone who put in this effort, it was kind of awesome to see.



357

00:58:10.320 --> 00:58:13.300

Technologic: Agreed, and thanks for bearing with me and Jay through this.



358

00:58:14.990 --> 00:58:16.320

Technologic: Alright, have everyone.



359

00:58:21.550 --> 00:58:24.430

Technologic: Alright, poker and beers at 5.30. Okay.



360

00:58:24.600 --> 00:58:40.560

Technologic: He's questioning 5.30, he's questioning now. So let me just crack open some cold ones, and then we'll… quickly. We'll knock out the… No, it's,



361

00:58:40.590 --> 00:58:55.480

Technologic: start with the chips. That's the time, that doesn't take too much time. Like, I remember one time Kevin was, like, he put in, like, a prompt to, like, set up the chips for poker, and, like, we took the whole game, some guy was, like.



362

00:58:55.570 --> 00:59:06.969

Technologic: Hey, does this make sense? The chips don't add up. I'm having, like, 2 hours in. And, like, tried to do math completely wrong. But anyways, do the chips.



363

00:59:07.300 --> 00:59:15.530

Technologic: The models are better. Yeah, to cut you. Okay, just a while.


