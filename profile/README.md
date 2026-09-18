# shishi-odoshi

<img alt="shishi-odoshi-transparent" src="https://github.com/user-attachments/assets/0cad2abb-5d79-441f-8a16-7fe3e35a6597" />

A *shishi-odoshi* (鹿威し) is the bamboo fountain that fills, tips, empties, knocks against its stone, and rights itself — on its own, forever. That's the property we want for Rails processes.

This org brings OTP-style supervision and crash-only design to the Ruby/Rails ecosystem without forking Rails: a slim supervisor that starts, links, health-checks, and restarts your web, jobs, cable, and cron processes with `one_for_one` / `rest_for_one` / `one_for_all` strategies, restart intensity, and backoff; resilience defaults for the places Rails apps actually fail; and, for those who want it, an Elixir/Phoenix sidecar that speaks the same protocols.

## Repos

Start with **[odoshi](https://github.com/shishi-odoshi/odoshi)** — everything else is optional.

| Repo | What it is | You want it if… |
|---|---|---|
| **[odoshi](https://github.com/shishi-odoshi/odoshi)** | The supervisor. Zero runtime dependencies; never loads Rails. [On RubyGems](https://rubygems.org/gems/odoshi). | …you have a Rails app whose processes should survive crashes |
| **[odoshi-template](https://github.com/shishi-odoshi/odoshi-template)** | A `rails new` template with chaos tasks that kill each process and assert recovery under 10s | …you want a working supervised app in one command |
| **[odoshi-resilience](https://github.com/shishi-odoshi/odoshi-resilience)** | Circuit breakers, a telemetry bridge, `Rails.supervisor.restart!`, and `bin/rails boot:check` | …you want crash-only conventions inside the app, not just around it |
| **[beam](https://github.com/shishi-odoshi/beam)** | Optional Elixir sidecar: supervises Rails processes as Ports, runs Solid Queue jobs, serves ActionCable-compatible channels | …you want BEAM concurrency beside Rails, sharing one Postgres |
| **[odoshi-bench](https://github.com/shishi-odoshi/odoshi-bench)** | Honest benchmarks vs foreman, overmind, `docker compose restart`, and bare | …you want the numbers before you trust the claims |
| **[odoshi-integration](https://github.com/shishi-odoshi/odoshi-integration)** | The whole stack running together under chaos, re-generated from source every CI run | …you want to see all of it work as one system |

Rails users never need the Elixir layer. Elixir users never need to read Ruby.

> Formerly published as `otp-rails`. Renamed in September 2026 — "otp" reads as *one-time password* in Rubyland, and this project's OTP was always the Erlang kind. Old repo URLs redirect; the `otp-rails` gem is a pointer release.

## Roadmap

Planned work lives on the [org roadmap board](https://github.com/orgs/shishi-odoshi/projects/1), grouped by milestone.

## Lineage

Grounded in Armstrong's [*Making Reliable Distributed Systems in the Presence of Software Errors*](https://erlang.org/download/armstrong_thesis_2003.pdf), Candea & Fox's [*Crash-Only Software*](https://www.usenix.org/legacy/events/hotos03/tech/full_papers/candea/candea.pdf) and [*Microreboot — A Technique for Cheap Recovery*](https://www.usenix.org/legacy/event/osdi04/tech/full_papers/candea/candea.pdf), and Nygard's [*Release It!*](https://pragprog.com/titles/mnee2/release-it-second-edition/).

