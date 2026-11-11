---
'@tanstack/react-router': patch
---

`MatchRoute` renders again only when its match changes, so a function child is no longer called once more, and the component it returns no longer renders again, while a navigation away from the matched route is pending.
