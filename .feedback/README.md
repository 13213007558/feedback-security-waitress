# Feedback task starting environment

Upstream: https://github.com/Pylons/waitress
Upstream commit: `2b43237e9caa66f906d0f652f2519cc79ef969a5`
Prepared on macOS with CPython 3.12.11. No external database, queue, or cloud account is required.
The dependency file pins the installed runtime and test packages for the selected baseline. It is not a claim that all optional upstream test suites are installed.

From the repository root:

```sh
uv venv --python 3.12 .venv
uv pip install --python .venv/bin/python -r .feedback/requirements.txt -e .
.venv/bin/python -m pytest -q -o addopts= tests/test_parser.py tests/test_receiver.py tests/test_channel.py tests/test_task.py
```

Observed baseline (2026-11-09): `323 passed, 45 subtests passed in 1.35s`
Whole-command wall time: 1.812 seconds, exit code 0. This is one local measurement, not a runtime guarantee. The first install is excluded.

This seed adds preparation metadata only. Application sources and upstream tests are unchanged; there is no task solution in this commit.
