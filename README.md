# Go Channel Loop Never Terminates

This repository demonstrates a common error in Go programs that use channels: a loop that never terminates because it waits indefinitely on a closed channel.

The bug is in the `main` function, which uses a `for...range` loop to receive values from a channel. The goroutine sends 10 numbers to the channel and then closes it. However, the `for...range` loop will keep waiting indefinitely, even after all the numbers have been received.

The solution modifies the loop to check for the channel's closed status and exit gracefully.