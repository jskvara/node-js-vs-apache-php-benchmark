# node-js-vs-apache-php-benchmark

This project shows performance tests for NodeJS (JavaScript server implementation) and Apache with PHP5 module.

This test was inspired by article [Benchmarking Node.js – basic performance tests against Apache + PHP](http://zgadzaj.com/benchmarking-nodejs-basic-performance-tests-against-apache-php). But that test was pretty unfair, because Apache sends much more headers.

In this test all unused headers were removed from Apache and some added to nodeJS. Same amount of data is send now from both Apache and nodeJS.

This benchmark was created in December 2010.
