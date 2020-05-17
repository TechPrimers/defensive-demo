# Defensive Demo
This DEMO project is WORK IN PROGRESS 

## REST endpoints
- `/actuator/chaosmonkey` - Chaos Monkey for Spring Boot
- `/employee/all` - Return employees from DB (H2)

## Chaos Experiments
Set virtual environment in python and install `chaostoolkit-spring`
```
python3 -m venv ~/.venvs/chaostk
source  ~/.venvs/chaostk/bin/activate
pip install chaostoolkit-spring
```
Run the experiment:
```
(chaostk)  chaostk  chaos run experiments.json
[2020-05-17 12:24:50 INFO] Validating the experiment's syntax
[2020-05-17 12:24:50 INFO] Experiment looks valid
[2020-05-17 12:24:50 INFO] Running experiment: Employee when database is down
[2020-05-17 12:24:50 INFO] Steady state hypothesis: Employee data is available
[2020-05-17 12:24:50 INFO] Probe: we-can-retrieve-employee-data
[2020-05-17 12:24:50 INFO] Steady state hypothesis is met!
[2020-05-17 12:24:50 INFO] Action: enable_chaosmonkey
[2020-05-17 12:24:50 INFO] Action: configure_assaults
[2020-05-17 12:24:50 INFO] Action: configure_repository_watcher
[2020-05-17 12:24:50 INFO] Steady state hypothesis: Employee data is available
[2020-05-17 12:24:50 INFO] Probe: we-can-retrieve-employee-data
[2020-05-17 12:24:50 INFO] Steady state hypothesis is met!
[2020-05-17 12:24:50 INFO] Let's rollback...
[2020-05-17 12:24:50 INFO] Rollback: disable_chaosmonkey
[2020-05-17 12:24:50 INFO] Action: disable_chaosmonkey
[2020-05-17 12:24:50 INFO] Experiment ended with status: completed

```