# Node.js VS Bun Performance Comparison
The focus of this comparison is solely on native HTTP servers

## Setup
- Your local machine
- [Bombardier](https://github.com/codesenberg/bombardier) as load testing tool 
- Stable Node.JS version v18.18.1
- Stable Bun version v.1.0.4


## Step
- In this assessment , there is series of test that is conducted.
- Each test involved the execution of 1 million requests under 2 different scenarios: 50 concurrent connections and 100 concurrent connections

### Examples
Testing 50 concurrent connections

Bun
- run command ```bun run bun-01/index.ts```
- do the load test run command ```bombardier -c 50 -n 1000000 http://localhost:3000 ```
- output
```
Bombarding http://localhost:3000 with 1000000 request(s) using 50 connection(s)
 1000000 / 1000000 [==========================================================================================================================================================================] 100.00% 95983/s 10s
Done!
Statistics        Avg      Stdev        Max
  Reqs/sec     96458.23   11537.58  125183.21
  Latency      515.77us    93.86us     4.01ms
  HTTP codes:
    1xx - 0, 2xx - 1000000, 3xx - 0, 4xx - 0, 5xx - 0
    others - 0
  Throughput:    17.47MB/s
```


Node.JS
- run command ```node node-01/index.mjs```
- do the load test run command ```bombardier -c 50 -n 1000000 http://localhost:3000 ```


