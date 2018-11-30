# Climbing route grading classifier

The [moonboard](https://www.moonboard.com) is a climbing training tool.  Each moonboard is a short identical climbing wall with the same holds, at the same orinentation in the same place.  There is a database of approximately 12,000 climbs held on the moonboard website to be used with a mobile app.  Each entry in the database describes which holds to use for the climb, gives it a difficult rating (grade) by given by the route setter and a crowd sourced grade given by the community, who have climbed the route.

Our aim is to predict the climbing grade only given the holds used for a climb.  This is a hard task - one which experienced climbers would find hard to do without climbing the route.  Even after climbing a route the route setter grade and the crowd source grade only agreed 95% of the time.

We experiment with three different loss functions to try and take advantage of the ordering of our labels (grades arranged on a number line).  This allows us to gain 70% accuracy (one out) using the CJS (cummlative Jensen-Shannon divergence) as our loss function compared to 65% accuracy using the standard cross-entropy loss.  For more details about the CJS loss see https://arxiv.org/pdf/1708.07089.pdf.  We also test the squared earth mover's distance (or Wasserstein metric) as a loss function but this gives worse results (60%) - https://arxiv.org/pdf/1611.05916.pdf.


Tasks and layout of the code:
- We scraped the data from the moonboard website in the [scraper notebook](https://nbviewer.jupyter.org/github/luke321321/portfolio/blob/master/climbing/Scraper.ipynb).
- We clean the data and analyise it in the [Data-cleaning-and-analysis notebook](https://nbviewer.jupyter.org/github/luke321321/portfolio/blob/master/climbing/Data-cleaning-and-analysis.ipynb).
- We fit a CNN (convolution neural network) model based upon ResNetv2 in the [CNN notebook](https://nbviewer.jupyter.org/github/luke321321/portfolio/blob/master/climbing/CNN.ipynb).

Result: we achieved 70% accuracy on the test dataset.

A picture of a moonboard:

<img src="moonboard.png" alt="a moonboard" width="300"/>