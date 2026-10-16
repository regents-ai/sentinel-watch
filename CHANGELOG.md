# Changelog

Each change to the check, newest first. A change takes effect when it lands on main.

## 16 Oct 2026

- The README now matches what the check and Sentinel do: GitHub starts the five-minute schedule about
  every two to five hours, and Sentinel warns after 6 hours without a run or after three failed runs.
- The schedule runs at two minutes past each five minutes, away from the top of the hour when GitHub
  is busiest and starts schedules late.

## 14 Oct 2026

- Code reviews check docs, Skills, tool and CLI drift (#1).
- The check runs every five minutes and asks Fly whether Sentinel's machine is running with its
  health check passing.
