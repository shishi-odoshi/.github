# shishi-odoshi

A *shishi-odoshi* (鹿威し) is the bamboo fountain that fills, tips, empties, knocks against its stone, and rights itself — on its own, forever. That's the property we want for Rails processes.

This org brings OTP-style supervision and crash-only design to the Ruby/Rails ecosystem without forking Rails: a slim supervisor that starts, links, health-checks, and restarts your web, jobs, cable, and cron processes with `one_for_one` / `rest_for_one` / `one_for_all` strategies, restart intensity, and backoff; resilience defaults for the places Rails apps actually fail; and, for those who want it, an Elixir/Phoenix sidecar that speaks the same protocols.

## Repos

- **`otp-rails`** — the supervisor. Zero runtime dependencies; never loads Rails.
- **`otp-rails-resilience`** — breakers, bulkheads, and crash-only conventions wired into ActiveRecord, Net::HTTP, and Redis.
- **`otp-rails-template`** — a `rails new` template with chaos tests that kill each process and assert recovery.
- **`beam`** — optional Elixir sidecar: supervises Rails processes as Ports, shares a job queue, fronts channels.

Rails users never need the Elixir layer. Elixir users never need to read Ruby.

## Lineage

Grounded in Armstrong's *Making Reliable Distributed Systems in the Presence of Software Errors*, Candea & Fox's *Crash-Only Software* and *Microreboot*, and Nygard's *Release It!*.
