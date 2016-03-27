## Backoff library with maximum number of calls

Usage:

Please do copy & paste the code, don't create more dependencies :)

```
// Retries the function f backing off the double of
// time each retry until a successfully call is made.
retry := backoff.NewDoubleTimeBackoff(100*time.Millisecond, 1*time.Second, 10)

// it would retry after 100 Millis, 200 Millis, 400 Millis, ..., up to 1 Second, 10 times in total
retry.Do(func() error {
  return MyLogic()
})
```
