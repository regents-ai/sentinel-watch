# Sentinel watch

Every five minutes, GitHub asks Fly whether Sentinel, the monitor that watches
every Regent site, is running and healthy. When it is not, the check fails and
GitHub emails the person who last changed the check's schedule.

Sentinel watches this check in turn: it warns when the check has not run for an
hour, or keeps failing while Sentinel is running.

The check reads Fly with a read-only key saved as this repository's
`FLY_API_TOKEN` secret. It prints only Sentinel's machine ids, states and
health check names.

GitHub pauses scheduled checks in a public repository after 60 days without a
commit. Sentinel's warning says so; turning the check back on from this
repository's Actions page starts it again.
