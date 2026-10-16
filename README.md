# Sentinel watch

GitHub asks Fly whether Sentinel, the monitor that watches every Regent site,
is running with its health check passing. The workflow
(`.github/workflows/check.yml`) is scheduled every five minutes, at two minutes
past, away from the top of the hour when GitHub is busiest. In practice GitHub
starts it far less often, about every two to five hours. When Sentinel is not
running, the check fails and GitHub emails the person who last changed the
check's schedule. A run can also be started by hand from this repository's
Actions page.

Sentinel watches this check in turn, reading its newest runs every fifteen
minutes. It warns by email and on its Alerts list, at most once a day each:

- when the check has not run for 6 hours;
- when its last three runs failed while Sentinel is running, which means the
  check itself is broken, most likely its Fly key.

The check reads Fly with a read-only key saved as this repository's
`FLY_API_TOKEN` secret (`fly tokens create readonly` for the regent
organization). It prints only Sentinel's machine ids, states and health check
names, since the run log is public.

GitHub pauses scheduled checks in a public repository after 60 days without a
commit. Sentinel's 6-hour warning covers that; turning the check back on from
this repository's Actions page starts it again.

Changes are listed in `CHANGELOG.md`.
