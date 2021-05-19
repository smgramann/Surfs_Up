# Surf’s Up – Weather Analysis

### Purpose

W. Avy would like to open an ice cream and surf shop in Hawaii, but wants to understand weather trends first.  He would like to see temperature data for the months of June and December in Oahu to help determine if this new business venture is sustainable year-round.

## Analysis

### Results

While the weather appears to not change dramatically between June and December, the analysis uncovered a few main differences referencing the two statistics tables below:


![June Stats](https://user-images.githubusercontent.com/80165223/118742927-f8545600-b816-11eb-9e3b-daa95387343e.png)


![December Stats](https://user-images.githubusercontent.com/80165223/118742960-04401800-b817-11eb-8f58-d1756bd716fe.png)



1)	The mean temperature in December is slightly lower (71 degrees) than the June mean temperature (75 degress) by approximately four degrees.

2)	The maximum temperatures in December and June are quite close.  Both are in the 80s and a difference of two degress.

3)	Minimum temperatures show the biggest difference between December and June.  December’s minimum temperature is 56 degrees while June’s minimum temperature is 64 degrees.

## Summary

As previously mentioned the temperature variation between December and June are, overall, minor and and suggest the likelihood of a year-round successful surf and ice cream shop.  To be sure, a couple other queries could be run:

1)	Build a statistics table for precipitation each month.  Below is an example of the query for the month of December:

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()

2)	Review the temperature data from the station that reports the most data to see if the location is viable for a surf shop.  Below is an example of the query for the month of December:

session.query(Measurement.tobs).\
filter(Measurement.station == ‘USC00519281’).\
filter(extract(‘month’, Measurement.date)==12).all()
