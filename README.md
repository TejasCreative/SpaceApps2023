# SpaceApps 2023: Develop the Oracle of DSCOVR

## Predicting Geomagnetic Storms with DSCOVR Data and Machine Learning

### Team It's Not Our Fault

By Tejas Bhartiya, Carolyn Cui, Gabriel Lee, Liam Morgan, Paul Stratton, Joshua Tapia

## Problem Statement

The Deep Space Climate Observatory, or DSCOVR, measures the strength and speed of solar winds in space. These measurements, in turn, help predict geomagnetic storms before they hit.

Geomagnetic storms occur when efficient energy exchange occurs between solar winds and the space environment around Earth; they can greatly affect systems like GPS, spacecraft, and electrical power grids.

The magnitude of a storm can be measured with a planetary K-index, which quantifies disturbances in Earth's magnetic field with a scale of 0 to 9. The greater the value, the more intense the geomagnetic storm. Only disturbances with a Kp value of 5 or greater qualify as geomagnetic storms.

DSCOVR's technology was ready years before its launch, and it's been in operation for over eight years now despite having an original mission life of just five years.

Thus, faults and anomalies have been rising in frequency and affecting the raw, or "level 1," data. These anomalies might have to do with the aging instruments, or they may actually be indicators of geomagnetic storms themselves.

The key instruments at play here are the PlasMAG fluxgate magnetometer and the Faraday cup; these instruments record the raw data.

This raw data, with readings at each minute, came in the form of

* x y z components of the sun's magnetic field in the geocentric solar ecliptic reference frame (GSE reference frame), and told us the direction in which the solar winds are traveling relative to Earth (measured in nanoTeslas)
* flow strength of solar wind (flux) and intervals in a range of flow speeds at which the wind is traveling (dimensionless data)

From the raw data, we can derive "level 2" data, which is data that has been processed to be human-readable. This level 2 data included things like solar wind density, speed, and temperature.

However, as we know, some of the data is faulty, meaning it may be unreliable for calculations.

As we approach the solar minimum, the declining phase of the solar cycle during which geomagnetic storms are most frequent, the ability to predict them would allow us to better prepare. So, how can we continue to use DSCOVR to accurately predict geomagnetic storms?

## Proposed Solution

After researching our problem to gain a deeper undersatnding, we found a pattern. The z-component of the magnetic field is perpendicular to Earth's ecliptic in the GSE reference frame. The more negative the z-component, the stronger the resulting storm.

There is one thing that's really good at patterns and reaching conclusions from them: machine learning models.

Through machine learning, we can circumvent the need for level 2 data by directly predicting the strength of geomagnetic storms before they arrive, given magnetic field vectors and the flow strength of solar wind.

All the processed raw data will be fed as input, and our expected output will be a Kp index.

We will evaluate numerous machine learning models to determine the most suitable means of predicting geomagnetic storms.

## Our Approach

The road to a solution can be broken into three parts:

1. Data Analysis and Processing

2. Model Development and Training

3. Results, Evaluation, and Presentation

## Data Analysis and Processing

### Data Issues

The raw data had a few issues that had to be addressed first before it could be used in our models.

The following are four of the most glaring issues we identified.

The most obvious problem, and the one that's hardest to detect, is the aforementioned issue regarding aging instruments. The raw data used for level 2 data has some anomalies, and we don't know what or where they might be.

Next, there was the problem of duplication: data sometimes repeated itself, especially in 2018, when thousands upon thousands of data points were duplicated. All of these had to be cleaned.

On top of duplication, there were even more NaN values. All satellite instruments were not operational all the time, leading to multi-month-long gaps in data collection and hundreds of thousands of missing values.

Lastly, we only had Kp values every three hours, while we had raw data points for every minute. We can't have 180 *x* values per every *y*. As the raw data tended to fluctuate significantly and a geomagnetic storm tends to last only a few hours, we settled on interpolation to solve this problem and fill in the gaps between K-indices.

### Processed Data

## Model Development and Training

## Results, Evaluation, and Presentation
