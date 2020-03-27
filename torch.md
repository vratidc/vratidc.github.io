---
title: Towards Accessible Spatial Audio Interfaces // Presentation Companion
permalink: torch
layout: single
author_profile: true
---

## Introduction

Listening to headings, but two at a time:

<audio controls>
        <source src="../media/torchaudio/1_TwoSpeakerSameVoice.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
</audio>
    



## The 5 Configurations

A sample audio file for each of the 5 configurations of variables can be found below. These are stereo recordings of the spatial audio file generated using [Resonance Audio](https://resonance-audio.github.io/resonance-audio/) and [Unity](https://unity.com/).

- **One Speaker**
    - Audio Clip:

    <audio controls>
        <source src="../media/torchaudio/2_OneSpeaker.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
    
    - Headline: **25000 personnel to watch over election counting in Maharashtra**
- **Two Speaker Same Voice**
    - Audio Clip

    <audio controls>
        <source src="../media/torchaudio/3_TwoSpeakerSameVoice.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
    - Headline 1: **25000 personnel to watch over election counting in Maharashtra**
    - Headline 2: **Will make efforts to simplify GST to improve biz ranking: Finance Minister**
- **Two Speaker Different Voice**
    - Audio Clip

        <audio controls>
        <source src="../media/torchaudio/4_TwoSpeakerDifferentVoice.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
        </audio>
    
    - Headline 1: **25000 personnel to watch over election counting in Maharashtra**
    - Headline 2: **Will make efforts to simplify GST to improve biz ranking: Finance Minister**
- **Three Speaker Same Voice**
    - Audio Clip

        <audio controls>
        <source src="../media/torchaudio/5_ThreeSpeakerSameVoice.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
        </audio>
    
    - Headline 1: **25000 personnel to watch over election counting in Maharashtra**
    - Headline 2: **Will make efforts to simplify GST to improve biz ranking: Finance Minister**
    - Headline 3: **CPI-M to launch 100 years celebration programme on Thursday**
- **Three Speaker Different Voice**
    - Audio Clip

        <audio controls>
        <source src="../media/torchaudio/6_ThreeSpeakerDifferentVoice.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
        </audio>
    
    - Headline 1: **25000 personnel to watch over election counting in Maharashtra**
    - Headline 2: **Will make efforts to simplify GST to improve biz ranking: Finance Minister**
    - Headline 3: **CPI-M to launch 100 years celebration programme on Thursday**

---

## Crafting the Task Prompt

***"You regularly follow Cricket, and often look for articles related to the Indian Cricket team whenever you read news headlines. In the following list of headlines, find the one that is most related to Indian Cricket."***

- Items 1 & 2

    <audio controls>
        <source src="../media/torchaudio/7_ListWindow1.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Items 3 & 4

    <audio controls>
        <source src="../media/torchaudio/8_ListWindow2.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Items 5 & 6

    <audio controls>
        <source src="../media/torchaudio/9_ListWindow3.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Items 7 & 8

    <audio controls>
        <source src="../media/torchaudio/10_ListWindow4.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Items 9 & 10

    <audio controls>
        <source src="../media/torchaudio/11_ListWindow5.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Items 11 & 12

    <audio controls>
        <source src="../media/torchaudio/12_ListWindow6.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
---

## Concurrent Speech

A base Indian Accent voice was initially chosen for further processing.

- Sample file of the base Indian accent female voice (Aditi, [Amazon Polly](https://aws.amazon.com/polly/))

    <audio controls>
        <source src="../media/torchaudio/13_AditiSample.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
Voice Synthesis using the [Praat Software](http://www.fon.hum.uva.nl/praat/) resulted in the following voice types:

- Androgynous Voice

    <audio controls>
        <source src="../media/torchaudio/14_AndrogynousPraat.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Male Voice

    <audio controls>
        <source src="../media/torchaudio/15_MalePraat.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>

- Female Voice

    <audio controls>
        <source src="../media/torchaudio/16_FemalePraat.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
For the final experiment, in addition to the base voice, two other American accent voices were used.

- Sample file of the American accent male voice (Matthew, Amazon Polly)

    <audio controls>
        <source src="../media/torchaudio/17_MatthewSample.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
    
- Sample file of the American accent female voice (Salli, Amazon Polly)

    <audio controls>
        <source src="../media/torchaudio/18_SalliSample.mp3" type="audio/mpeg">
        Sorry but it seems that your browser does not support the audio element.
    </audio>
---

## Curated Task Lists and Prompts

**1**

***You regularly follow Cricket, and often look for articles related to the Indian Cricket team whenever you read news headlines. In the following list of headlines, find the one that is most related to Indian Cricket.***

1. One in every six missing children from Bengal: NCRB
2. Israel PM Netanyahu says he has failed to form government
3. **I was rejected in my first selection trials, reveals Sachin Tendulkar**
4. Link between unique brain cells and OCD and anxiety discovered
5. Drone images reveal shrinkage of Iceland's glaciers since 1980s
6. From beach clean-up to khadi fest, Mumbai honours the Mahatma
7. Solomon Islands vetoes China's attempt to lease its island
8. 6 suffer burns in Wadala after cat comes in contact with power line
9. Trump suspends Thailand's $1.3 billion trade preferences
10. Arsenal lose to Sheffield, miss chance to enter top-four
11. Ranveer enjoys process of acting more than results: Kabir Khan
12. German Chancellor Merkel to visit India on November 1

**2**

***You have just had a conversation with your friend regarding sportspersons and athletes entering politics. In the following list of headlines, find the one that is most related to the conversation.***

1. T20 World Cup next year is a big focus for us: Virat Kohli
2. Karnataka defeat Tamil Nadu to win Vijay Hazare Trophy for 4th time
3. Four officers killed in knife attack at Paris police HQ
4. Once Upon a Time in Hollywood' to re-release with 4 new scenes
5. **Ex-hockey captain Sandeep wins, wrestlers Babita, Yogeshwar lose elections**
6. Longest non-stop passenger flight lands in Sydney after 19 hours in the air
7. Chandra Observatory spots collision between 4 galaxy clusters
8. Universe's first-ever colour was an orange-white glow: Study
9. Theatre, art should be part of school curriculum: VP Naidu
10. Four-fold hike in monetary aid announced for battle casualties
11. 25-year-old pillion rider crushed to death in Mumbai after vehicle hits pothole
12. Noida-based Dixon Technologies to manufacture Samsung phones

**3**

***You like to keep track of the state of politics in Maharashtra, and especially the results of the recent elections. In the following list of headlines, find the one that is most related to the Maharashtra Elections.***

1. Rajasthan Royals appoint Andrew McDonald as new head coach
2. **After rejecting Sena's request for time, State Gov invites NCP to form govt**
3. Assyrian tablets oldest-known recorded evidence of auroras
4. Kurt Cobain's sweater with burn hole sold for ₹2cr 25 yrs after he died
5. India takes Pak to world body for denying airspace use to PM: Report
6. Bandra-bound train derails, services held up for 4 hours
7. Prakash Javadekar defends hacking of trees ahead of PM Modi’s rally
8. Messi becomes 1st player to score in 15 straight Champions League seasons
9. United end Liverpool's winning run in PL with a 1-1 draw
10. UAE to invest $5 billion in Pak. oil refinery project, says report
11. Sensex jumps over 250 points on Muhurat trading
12. Blueprint made for 'quantum battery' that doesn't leak charge
13. Darjeeling tea workers to get 20 percent bonus

**4**

***You have just heard of an accident in the Mumbai Local, near Navi Mumbai. In the following list of headlines, find the one that is most related to that accident.***

1. Joker' surpasses 'Deadpool 2' to become biggest R-rated film ever
2. Curiosity rover takes selfie on Mars; NASA shares picture
3. My throat hurts all the time: Maria Sharapova on grunting during matches
4. **Train catches fire at Vashi, Harbour Line services hit**
5. SC bench to hear Aarey forest case on Monday
6. Russia sends nuclear bombers to South Africa on training mission
7. RCB become first IPL team to hire a woman in support staff
8. Indonesia's Joko Widodo sworn in for second term as President
9. India speaks to U.S. lawmakers prior to human rights hearing
10. Avengers assemble at battleground High Street Phoenix, Mumbai
11. Virgin Galactic to become 1st public space tourism firm on Monday
12. Scientists make artificial skin that senses tickling, pinching

**5**

***When reading the news, you often look for articles about movies and entertainment, especially Bollywood and Hindi Cinema. In the following list of headlines, find the one that is most related to Bollywood.***

1. Three arrested for selling bogus driving licences in Navi Mumbai
2. C.V. Raman ‘possibly’ forced to leave Calcutta: Abhijit Banerjee
3. New Delhi and Dhaka fail to ink deal on river waters
4. Climate change to lead to more frequent extreme El Niño: Study
5. I once secretly took pic of Momoa on a plane: 74-yr-old Helen Mirren
6. BSNL, MTNL to be merged; government announces 15,000 crore revival plan
7. Federer beats Tsitsipas in Basel semis for 50th win of season
8. IITian's nanosatellite system produces high-res images at low cost
9. Hong Kong pro-democracy protesters rally for Catalan separatists
10. **I've written 'Dabangg 3', so it's for the critics: Salman Khan**
11. Praja Foundation picks holes in BMC’s malaria, TB death figures
12. Jailed former Pakistan PM Nawaz Sharif granted bail on medical grounds

**6**

***When reading the news, you often look for articles about movies and entertainment, especially Bollywood and Hindi cinema. In the following list of headlines, find the one that is most related to Bollywood.***

1. Missing teen from Mumbai traced to hospital in Kolkata
2. **Amitabh Bachchan shares old letter written to him by young Abhishek**
3. Pakistan, Afghan Taliban call for resumption of peace talks
4. India has taken good step on corporate tax rate: World Bank Prez
5. India’s first e-waste clinic to be set up in Bhopal
6. Rooney to take player-coach role at Derby after MLS exit
7. India declared when it was dark in every Test: Faf du Plessis
8. Rain sets new Monsoon record in Mumbai and Maharashtra
9. Critical 'reheating' period that kickstarted Big Bang simulated
10. Scorsese, Coppola can criticise Marvel: 'Iron Man' director
11. SC gives tax relief for food at incorporated clubs
12. Japan's Emperor Naruhito ascends throne, Prez Kovind attends ceremony

**7**

***You like to read news about India’s relationship with the world, and India-Pakistan relations in particular. In the following list of headlines, find the one that is most related to India-Pakistan relations.***

1. Glacial rivers absorb CO2 faster than rainforests: Study
2. One day I will be the President of the US: Rapper Kanye West
3. Maharashtra hospitals face shortage of mental health professionals
4. SoftBank says it has now invested more than Bolivia's GDP in WeWork
5. Next three PSLV missions will carry 14 small foreign satellites
6. Notice to UIDAI on linking property documents with Aadhaar numbers
7. **PM Modi thanks Pak PM Imran Khan for cooperation on Kartarpur Corridor**
8. Trump suggests Adam Schiff should be arrested for ‘treason’
9. Researchers identify song-learning neurons in songbirds
10. Convicted Russian spy arrives in Moscow after deportation from US
11. Paralympian who slept 10 minutes some nights ends life by euthanasia
12. I am like everyone else but I just control my emotions better: MS Dhoni

**8**

***You like to keep in touch with the latest advancements in space exploration. In the following list of headlines, find the one that is most related to space travel and exploration.***

1. Post-monsoon showers pelt Konkan, bring relief to Marathwada
2. Australia PM carries drinks for players during cricket match, pic goes viral
3. Justin Trudeau wins 2nd term as Canada's Prime Minister
4. New world record for smallest image sensor in market
5. Major fire breaks out in Mumbai arcade, 7 rescued
6. Scientists discover new stable form of plutonium by accident
7. India, China have a very good understanding: ITBP chief
8. Northern Ireland decriminalises abortion and same-sex marriages
9. **Humans can be landed on Mars by 2035, says NASA chief**
10. US, China close to finalising some parts of trade deal: USTR
11. Seat-distribution in Maharashtra is more frightful than partition: Sanjay Raut
12. Lost almost 5 kg, it is fantastic: Amitabh after returning from hospital

**9**

***You are often interested in world politics. In the following list of headlines, find the one that is related to an incident involving the US President.***

1. **Donald Trump fined $2 million for misusing namesake charity**
2. 2019 Ozone Hole is the smallest on record since discovery: NASA
3. Vistara to fly from Mumbai to Colombo from next month
4. Bengaluru to host World Coffee Conference in September 2020
5. Some at Barcelona didn't want Neymar to return: Lionel Messi
6. Shah’s chopper makes emergency landing in Nashik due to rains
7. 40 killed as anti-govt protests turn violent in Iraq: Reports
8. Hong Kong withdraws extradition bill that sparked months-long protests
9. Neymar not among Ballon d'Or nominees, Liverpool dominate with 7 names
10. With NBA, Mumbai-born Vivek Ranadive builds a bridge across the seas
11. Adult flies experienced 'ageing' on blue light exposure: Study
12. ITC, Pune cooperative team up to recycle chips, biscuit packets

**10**

***You have just heard that there almost was an aeroplane accident in India yesterday night. In the following list of headlines, find the one that is most related to that incident.***

1. Shetty-Rankireddy 1st Indian men's duo in a World Tour Badminton final
2. My heroes were playing under me: Kapil Dev recalls his captaincy
3. ISIS leader Baghdadi blew himself up during US raid, confirms Trump
4. Archaeologists uncover 2,000-year-old street in Jerusalem
5. Most of 39 UK truck victims were likely from Vietnam: Reports
6. Lawyer exhibits art at Asian Heart Institute in Bandra
7. Rishi Kapoor scolds media outside Diwali party over noise, video surfaces
8. PM moots ‘Einstein Challenge’ in tribute to the Mahatma
9. Japan imported Ebola ahead of Olympics to be prepared
10. Tesla is a competitor we take very seriously: Volkswagen CEO
11. **IndiGo flight with 180 passengers makes emergency landing in Goa**
12. Wholesale onion prices fall below ₹30/kg at Lasalgoan in Maharashtra

**Training List 1**

***Your friend works in a phone company. While talking to you on call, he asked you to check today’s headlines for news about Indian Telecom (telecommunications) companies. In the following list of headlines, find the one that is most related to the conversation.***

1. Duty-free shops at Mumbai airport eligible for GST refund says HC
2. Chile Prez Piñera announces social measures to stem protests
3. Officials in J&K worried over posting to Union Territories
4. Ahmedabad-based NGO creating database of stem cell donors
5. UK PM calls for snap general election on December 12
6. **MPs want to ditch BSNL, MTNL over poor service**
7. Mahindra & Mahindra to fully acquire France's Peugeot Motocycles
8. Favourable wind speed keeps pollution levels in check in Delhi
9. Mumbai BJP president Lodha declares assets worth ₹441 crore
10. Andy Murray wins his first title since March 2017
11. My dream is to play and win World Cup for India: Sanju Samson
12. 3000-year-old tombs found with the help of scent-tracking dogs

**Training list 2**

***You regularly follow Cricket, and often look for articles about the Indian Cricket team whenever you read news headlines. In the following list of headlines, find the one that is most related to Indian Cricket.***

1. Centre to release Rs. 1200 cr. for Karnataka floods
2. Belgium names Sophie Wilmes as its first female PM
3. 25000 personnel to watch over election counting in Maharashtra
4. Will make efforts to simplify GST to improve biz ranking: Finance Minister
5. Govt can't dictate Olympic selection terms to federations: Rijiju
6. Molecular structure predicted by Nobel winner 126 years ago found
7. 4 killed, 5 wounded in overnight shooting at Kansas bar
8. World's fastest ants found in Sahara desert, reveal researchers
9. Botched eye surgeries: operating doctors, KEM Hospital pulled up
10. **I would like Virat Kohli to focus on winning ICC tournaments: Ganguly**
11. CPI-M to launch 100 years celebration programme on Thursday
12. Marvel films are a new art form: Filmmaker Scorsese

**Training list 3**

***You are interested in news related to business and technology. You have heard about an incident involving two major technology companies competing with each other. In the following list of headlines, find the one that is most related to the incident.***

1. Jadeja best Indian fielder in last decade: Team India fielding coach
2. Vast population of venomous sea snakes found by grandmothers' group
3. PM Modi to meet King Salman in Saudi Arabia on October 29
4. **Microsoft beats Amazon, wins US' $10-billion JEDI defence contract**
5. Ticket prices as low as ₹50 for India-Bangladesh Test in Kolkata
6. Surviving tongue cancer made me grateful: Actor Michael Douglas
7. National Conference delegation to meet Farooq and Omar today
8. 109 tonnes plastic waste found at Western Railway stations
9. Activists dispute Mumbai Metro claim on number of trees cut
10. Ready for bold steps to push Air India sale: Puri
11. New technique aims to detect stranded whales from space
12. Ex-US Prez Carter, aged 95, hospitalised after fall at home

**Training list 4**

***You are interested in business news and the economic situation of the country. In the following list of headlines, find the one that is most related to the economic and financial situation in India.***

1. Ex-Apple lawyer for insider trading indicted for insider trading
2. Two out of three wild poliovirus strains eradicated: WHO
3. US military no longer using floppy disks to control nuke launches
4. Kuch Kuch Hota Hai lacked logic, SRK's character had no spine: Karan
5. Ronaldo earns more from his Instagram posts than from playing for Juventus
6. Mumbai monuments win big at UNESCO restoration awards
7. **World Bank to continue with $6 billion annual lending target for India**
8. In Vikhroli, State’s sole disabled candidate takes on NCP, Sena
9. Ahead of Dussehra, plastic Ravana emerges as the new villain
10. Fossils of species that survived dinosaur-killing asteroid found
11. Nick Jonas celebrates Diwali with Priyanka in Mexico; shares pic

**Training list 5**

***You regularly follow Cricket, and often look for articles about the Indian Cricket team whenever you read news headlines. In the following list of headlines, find the one that is most related to Indian Cricket.***

1. **Kohli agreeable to India playing Day-Night Tests: BCCI President Ganguly**
2. Over 100 kg sandalwood seized from Mumbai airport in past 10 days
3. US astronauts share their pics from NASA's 1st all-female spacewalk
4. Radioactive chlorine from 1950s bomb tests found in Antarctica
5. Samsung's Senior Global VP Pranav Mistry named STAR Labs CEO
6. Forced to remove hoardings after police detention: Mumbai locals
7. Wounds of demonetisation, GST have now become deeper: Akhilesh Yadav
8. Bangladesh seeks visa on arrival for its tourists in India
9. Scottish whisky, French cheese come under U.S. trade tariffs
10. Europol launches campaign to catch Europe's 'most wanted women'
11. Singer Miley Cyrus undergoes vocal cord surgery: Reports
12. Ranveer Singh recreates Kapil's iconic Natraj shot, shares pic