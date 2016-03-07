## Backoff library with maximum number of calls

Usage:

Please do copy & paste the code, is just one function, don't create more dependencies :)

```
// Do retries the function f backing off the double of time each retry until a successfully call is made.
// initialBackoff is minimal time to wait for the next call
// maxBackoff is the maximum time between calls, if is 0 there is no maximum
// maxCalls is the maximum number of call to the function, if is 0 there is no maximum
func Do(initialBackoff, maxBackoff time.Duration, maxCalls int, f func() error) error {...}
```

For example

```
err := Do(100*time.Millisecond, 30*time.Second, 10, func() error {
  return MyLogic()
})
```
