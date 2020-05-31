
{% include prezi.html %}

A project in response to [SpaceApps COVID-19 Challenge](https://covid19.spaceappschallenge.org): [A New Perspective](https://covid19.spaceappschallenge.org/challenges/covid-challenges/a-new-perspective)

# Noise around us
Are birds louder these days? Turns out so many people noticed this, that it started to reflect in web search trends.

{% include birds_are_louder.html %}

One possible explanation is the lower overall noise level in cities and beyond (see also: [The Quiet Planet](https://covid19.spaceappschallenge.org/challenges/covid-challenges/quiet-planet) challenge.) We asked ourselves:

> Would a similar thing also happen under the sea?

# Noise pollution in the time of pandemic
Noise pollution has been a growing concern among marine biologists. Increase in maritime traffic for both leisure and fishing purposes, military activity, offshore drilling are just a few examples of sources of unwanted sounds affecting some marine mammals, which depend on mechanisms like echolocation. Our understanding of the complex relation between our loud activities and ocean life is yet to be expanded. However, the present times posed a unique opportunity to research an acute drop in human racket.

As part of safety precautions during the COVID-19 pandemic, many coastal areas declared suspension of all non-essential maritime traffic. This has had a number of effects: the diminished number of traveling vessels leads to reduced noise pollution, decreases water turbidity as seen in Venice, but also limits the capability of marine biologists to perform measurement activities. Is the data out there ready to prove the link?

# Maritime traffic

{% include traffic.html %}

We investigated the maritime traffic. While AIS data is abundant online, many of the sources do not meet the criteria of openness while some others not yet provide the timeframes required for accurate determination of the changes as results of restrictions caused by the pandemic.

One of the sources that presents the ongoing changes in the maritime traffic can be found at [12]. Comparison of vessels and route density in March 2020 with the same period last year shows a significant reduction in human activity on the European waters. The same source reports a drop in fishing activities by nearly 40% on Western Mediterrean Sea, compared to the previous year.

One can hypothesize this leads to an equivalent reduction in sea water parameters like turbidity and noise pollution. However, we have not obtained the data to sufficiently prove the link as those were not yet available for the required timeframe.

# Digital recognition of marine mammals
We created a whale detection engine, based on the paper released as a part of ESA’s project SPACE WHALE. A Convolution Neural Network (CNN) was trained to recognize cetaceans on the satellite and aerial pictures.
Training pictures containing whales were obtained from [17].

{% include image.html url="training_whales.png" description="Sample images used to train the neural network. Obtained from the NOAA photo library" %}

Enclosed below is a snippet from the training process output. Diminishing loss value can be observed:
```
INFO:tensorflow:loss = 15.694896, step = 0
I0531 16:03:02.523565 140498314856320 basic_session_run_hooks.py:262] loss = 15.694896, step = 0
INFO:tensorflow:global_step/sec: 0.406591
I0531 16:07:08.469161 140498314856320 basic_session_run_hooks.py:692] global_step/sec: 0.406591
INFO:tensorflow:loss = 5.306469, step = 100 (246.082 sec)
I0531 16:07:08.604288 140498314856320 basic_session_run_hooks.py:260] loss = 5.306469, step = 100 (246.082 sec)
INFO:tensorflow:global_step/sec: 0.409948
I0531 16:11:12.402760 140498314856320 basic_session_run_hooks.py:692] global_step/sec: 0.409948
INFO:tensorflow:loss = 3.683988, step = 200 (243.800 sec)
I0531 16:11:12.404425 140498314856320 basic_session_run_hooks.py:260] loss = 3.683988, step = 200 (243.800 sec)
INFO:tensorflow:Saving checkpoints for 240 into /tmp/tmpeelow2fh/model.ckpt.
```
Such a neural network can be subsequently used on two sets of test aerial images, taken at different points in time, in order to compare number of animal occurences in some specific areas.

Code for the neural network can be found in the [project repository][18].

# Conclusions
- The pandemic impacts also the marine life, in multiple ways
- The reduced capacity of performing manual data gathering activities during pandemic restrictions can be offset by automation efforts, with the help of AI and remote sensing
- Aerial photography can be successfully used to detect cetaceans on ocean surface

# Into the future
This is just a small glimpse of the possible areas for investigation. If the data from February to May 2020 could be obtained from regular hydrophone measurements and GPS trackers of cetacean specimen, more knowledge could be inferred about the response of the aquatic life to the sudden change in human activity. Combining with even more sources, like data from the [WhaleWatch project][16], may yield even more interesting results.

# References
ESA resources:
- \[1] [Project SPACE WHALE][1]
- \[2] [A. Borowicz et al., Aerial-trained deep learning networks for surveying cetaceans from satellite imagery*][2]

COVID-19 impact:
- \[3] [Quiet oceans: Has the COVID-19 crisis reduced noise in whale habitats?][3]
- \[4] [Ocean Sound in COVID-19 Era][4]

Noise affecting marine mammals:
- \[5] [Behavioral Changes Tutorial at Discovery of Sound in the Sea][5]
- \[6] [R.M. Rolland et al., Evidence that ship noise increases stress in right whales][6]
- \[7] [Listening To The Sea: Using Passive Acoustic Data to Monitor Ships and Ocean Life][7]
- \[8] [S. Veirs et al., Ship noise extends to frequencies used for echolocation by endangered killer whales][8]
- \[9] [Beluga Mother and Calf Communication \| Notes From The Field \| Ocean Wise (YouTube)][9]

Maritime traffic:
- \[10] [Vessel ID System][10]
- \[11] [National Ocean Service: What is ocean noise?][11]
- \[12] [COVID-19 impact on fishing][12]

Marine mammal presence detection:
- \[13] [E. Guirado et al., Whale counting in satellite and aerial images with deep learning][13]
- \[14] [NOAA Kaggle Challenge: Right Whale Recognition][14]
- \[15] [BelugaSounds: Using machine learning to detect beluga whale calls in hydrophone recordings][15]
- \[16] [WhaleWatch program][16]
- \[17] [NOAA photo library]

\* the paper is an outcome of the SPACE WHALE project funded by ESA.


[1]: https://business.esa.int/projects/spacewhale
[2]: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0212532
[3]: https://www.aquablog.ca/2020/04/quiet-oceans-has-the-covid-19-crisis-reduced-noise-in-whale-habitats/
[4]: https://iqoe.org/articles/ocean-sound-covid-19-era
[5]: https://dosits.org/tutorials/effects-introduction/behavioral-changes/
[6]: https://royalsocietypublishing.org/doi/full/10.1098/rspb.2011.2429
[7]: https://noaa.maps.arcgis.com/apps/Cascade/index.html?appid=c653c78262a7487da42149ebc86f80c2
[8]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4800784/
[9]: https://www.youtube.com/watch?v=GLlNXd1dJkA
[10]: https://www.nasa.gov/mission_pages/station/research/news/b4h-3rd/eo-tracking-global-marine-traffic
[11]: https://oceanservice.noaa.gov/facts/ocean-noise.html
[12]: https://www.emodnet-humanactivities.eu/blog/?p=1258
[13]: https://www.nature.com/articles/s41598-019-50795-9
[14]: https://www.kaggle.com/c/noaa-right-whale-recognition/data
[15]: https://github.com/Microsoft/belugasounds
[16]: https://www.fisheries.noaa.gov/west-coast/marine-mammal-protection/whalewatch
[17]: https://www.photolib.noaa.gov/Collections
[18]: https://github.com/HummingWaves/hummingwaves