Benchmarking Nginx
------------------

Nginx is a popular open-source web server software that is widely used for handling high-traffic websites and applications. It is known for its high performance, scalability, and low resource consumption. One of the key advantages of using Nginx is its ability to handle a large number of concurrent connections without sacrificing performance.

Benchmarking is the process of measuring the performance of a system or application under specific conditions. Nginx benchmarking involves testing the performance of the Nginx web server under various conditions, such as the number of concurrent connections, the size of the request, and the type of request.

By benchmarking Nginx, you can gain insights into its performance characteristics and identify potential bottlenecks that may impact its ability to handle high traffic loads. This information can be used to optimize the configuration of Nginx and ensure that it can handle a large number of requests efficiently.

In this context, Nginx benchmarking typically involves running a series of tests that simulate real-world traffic loads and measuring the response time, throughput, and other performance metrics. This data can be used to evaluate the effectiveness of various optimizations and configurations, such as load balancing, caching, and SSL acceleration.

Overall, Nginx benchmarking is an important process for anyone looking to optimize the performance of their web server and ensure that it can handle high traffic loads without sacrificing performance.

Measurements
------------

1. P99 latencies using wrk2 
2. throughput (Requests/second)
3. Data transfer (per second) Could be a use case for content delivery networks.


Client
------

wrk2 can be used as a client to stress nginx with single or multiple end points.

1. To test http connections, throughput over a simple web page

   ```./wrk -L -t 10 -c 1000 -d 30 -R 10000 http://nginxserverip:port```

2. To test secure https connections, throughput over a simple web page

   ```./wrk -L -t 10 -c 1000 -d 30 -R 10000 https://nginxserverip:port```

3. To test secure data transfer throughput over a network

   ```./wrk -L -t 10 -c 1000 -d 30 -R 10000 https://nginxserverip:port/1mb_file.txt```

	here any file size can be used 1m_file.txt is just example, generate files for
    nginx server, it can have just one file or multiple random files.
