---
'@tanstack/start-server-core': patch
---

The server handler caches its entries, base manifest and final manifest once they have loaded, instead of sharing the first request's pending load with every later request. On Cloudflare Workers, a promise only settles in the request that created it, so cancelling the first request while one of these loads was pending made every later request of the isolate fail with 500. Requests that arrive before the first load finishes now each start their own load.
