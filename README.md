# Role-rule commitments

Public commitments to rules that were fixed before a public random number existed.

Each `role_rule_v<N>.txt` states the SHA-256 of a rule (code and inputs), the time `T_BEACON`, and
the round of the drand "quicknet" beacon whose randomness the rule uses. The rule assigns the people
of a research benchmark (EEG to intracranial recordings) to a development or a test role. Nobody can
know the beacon before `T_BEACON`, and fixing the rule before it removes any choice over the result.

- Each commitment file is written once, in a single commit, and never changed. Pushes to this public
  repository are recorded by GitHub and by GH Archive.
- `role_rule_v<N>.txt.ots` is an OpenTimestamps proof of that file, anchored in Bitcoin (added once
  the proof is complete). Check it with `ots verify role_rule_v3.txt.ots`.
- The rule code is released with the benchmark. Anyone can then check that the SHA-256 of
  `src/paired/splits/roles.py` followed by `src/paired/splits/exposed_people.tsv` equals `rule_sha256`:

      cat src/paired/splits/roles.py src/paired/splits/exposed_people.tsv | sha256sum

- The beacon value is public at `https://api.drand.sh/<chain>/public/<round>`.

No data, code or personal information is kept here.
