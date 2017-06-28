# SamKnows Technical Test (PHP/MySQL)

> This is the technical test for our back-end (PHP/MySQL) positions at SamKnows. If you just stumbled across this and you are interested in joining our team, go to [our careers page](https://samknows.com/careers) to see if we are hiring.

Thank you for your interest in becoming part of SamKnows. We would like you to complete the technical test below; We're excited to see your solution!

Before we start, we want to give you an idea of what we are looking for and what should be considered for your solution. For instance, while we do use Symfony 3 at SamKnows, for this particular test we ask you not to use any framework (packages are encouraged though!).

This should roughly take you three hours. If you'd like to do more, but don't have time then please mention it in your README.

## Dont’s
- *Do not* use any full-stack frameworks (e.g. `symfony/symfony` or `laravel/laravel`)
- *Do not* use anything other than MySQL or SQLite
- *Do not* use Docker, Vagrant or similar

## Do’s
- *Do* use appropriate packages (e.g. `symfony/console` or micro-frameworks)
- *Do* use unit tests
- *Do* use good design patterns
- *Do* use dependency management
- *Do* use efficient database schema
- *Do* use consistent code styles
- *Do* elaborate on what you would do, given the time

## The Challenge
For your test we are providing you with a JSON (see structure below). It contains a variety of “units” (A unique device which reports data) and data points for specific metrics that they tested between 1st and 30th of February 2017. Those units tested download and upload speed, as well as latency and packet loss.

Your task is to fetch the data (whenever the application runs) and pre-process it to create an aggregated table. This should act as a store to see how good or bad every hour in the day performed. Imagine that instead of a few thousand, you would have to deal with trillions of data points – a reality for us at SamKnows!

*So we would like for you to…*
1. Aggregate all data points per unit, metric and hour
2. Calculate the “mean“, “minimum“, “maximum“, and “median“ as well as “sample size“ for every hour (01 to 24)
3. Persist the data into an efficient and optimised database schema

Your solution needs to enable us to check a specific unit & metric (e.g. unit #1's download results) of a specific hour in the day (e.g. 9am or 1pm), show the min, max, mean and median, as well as the number of data points in that dataset.

## JSON
Available here: `http://tech-test.sandbox.samknows.com/php-2.0/testdata.json`

The structure is pretty simple and contains a few units for which we will give you 4 metrics (`download`, `upload`, `latency` and `packet_loss`. Every one of those metrics contains a large amount of data points with `timestamp` and `value`.

```javascript
[
  {
    "unit_id": 1,
    "metrics": {
      "download": [
        {
          "timestamp": "2017-02-10 17:00:00",
          "value": 4670170
        }
	// [...]
      ],
      "upload": [
        {
          "timestamp": "2017-02-28 17:00:00",
          "value": 1214720
        },
	// [...]
      ],
      "latency": [
        {
          "timestamp": "2017-02-22 16:00:00",
          "value": 44868
        },
	// [...]
      ],
      "packet_loss": [
        {
          "timestamp": "2017-02-08 05:00:00",
          "value": 0.12
        },
	// [...]
      ]
    }
  },
  [...]
}
```

## Test Considerations

As mentioned above, we are particularly looking at unit tests, packages used, design patterns implemented, dependency management, the commits you made, appropriate database schema, consistent coding style and a few more things. We really want to get a good idea of how you structure your code architecture and how clean and efficient your code and database is.

Last but not least, please make sure you test your code and make it as easy to run as possible (i.e. provide a descriptive and well-formatted README).

Good luck!
