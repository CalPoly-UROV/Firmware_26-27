# Contributing to PX4-Autopilot

We follow the [GitHub flow](https://guides.github.com/introduction/flow/) development model.

## Create a feature branch

Always branch off `main` for new features. Branches should be named as such: Name-Feature-StartDate. 

```
git checkout -b mydescriptivebranchname
```

## Edit and build the code

The [developer guide](https://docs.px4.io/main/en/development/development.html) explains how to set up the development environment on Mac OS, Linux or Windows.


## Push your changes

Push changes to your repo and send a [pull request]

Make sure to include of a description of the work you are pushing. The only people who should be approving pull requests are Raymond or Sahaana.

### Scopes

The scope identifies which part of PX4 is affected. Common scopes:

| Scope | Area |
|-------|------|
| `ekf2` | Extended Kalman Filter (state estimation) |
| `mavlink` | MAVLink messaging protocol |
| `commander` | Commander and mode management |
| `navigator` | Mission, RTL, Land, and other navigation modes |
| `sensors` | Sensor drivers and processing |
| `drivers` | Hardware drivers |
| `boards/px4_fmu-v6x` | Board-specific changes (use the board name) |
| `mc_att_control` | Multicopter attitude control |
| `mc_pos_control` | Multicopter position control |
| `fw_att_control` | Fixed-wing attitude control |
| `vtol` | VTOL-specific logic |
| `actuators` | Mixer and actuator output |
| `battery` | Battery monitoring and estimation |
| `logger` | On-board logging |
| `param` | Parameter system |
| `simulation` | SITL, Gazebo, SIH |
| `ci` | Continuous integration and workflows |
| `docs` | Documentation |
| `build` | CMake, toolchain, build system |
| `uorb` | Inter-module messaging |

For changes spanning multiple subsystems, use the primary one affected. Look at the directory path of the files you changed to find the right scope: `src/modules/ekf2/` uses `ekf2`, `src/drivers/imu/` uses `drivers/imu`, `.github/workflows/` uses `ci`.

### Good commit messages

```
feat(ekf2): add height fusion timeout
fix(mavlink): correct BATTERY_STATUS_V2 parsing
refactor(navigator): simplify RTL altitude logic
ci(workflows): migrate to reusable workflows
docs(ekf2): update tuning guide
feat(boards/px4_fmu-v6x)!: remove deprecated driver API
perf(mc_rate_control): reduce loop latency
```

### PR titles

The PR title follows the same `type(scope): description` format. 

