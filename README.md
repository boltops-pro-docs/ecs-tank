<!-- note marker start -->
**NOTE**: This repo contains only the documentation for the private BoltsOps Pro repo code.
Original file: https://github.com/boltopspro/ecs-tank/blob/master/README.md
The docs are publish so they are available for interested customers.
For access to the source code, you must be a paying BoltOps Pro subscriber.
If are interested, you can contact us at contact@boltops.com or https://www.boltops.com

<!-- note marker end -->

# Ecs Tank

[![Watch the video](https://img.boltops.com/boltopspro/video-preview/tools/ecs-tank.png)](https://www.youtube.com/watch?v=mDU_Lm5xhig)

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

Quickly drain and fill ECS Container instances associated with resources like spot fleet requests or autoscaling groups.  This is useful for maintenance.

## Installation

    git clone git@github.com:boltopspro/ecs-tank
    cd ecs-tank
    rake install

## Usage

    ecs-tank drain INSTANCE_ID --cluster CLUSTER
    ecs-tank drain SPOT_FLEET_ID --cluster CLUSTER
    ecs-tank drain AUTOSCALING_GROUP_ID --cluster CLUSTER

    ecs-tank fill INSTANCE_ID --cluster CLUSTER
    ecs-tank fill SPOT_FLEET_ID --cluster CLUSTER
    ecs-tank fill AUTOSCALING_GROUP_ID --cluster CLUSTER

    ecs-tank list CLUSTER
    ecs-tank info INSTANCE_ID

## Examples

Drain commands:

    $ ecs-tank drain i-0d149035a429fe23a --cluster development
    Finding Instance: i-0d149035a429fe23a
    Updating container instances with status DRAINING:
    1a4ece6726304582bdc89dfe0e6ce849 (i-0d149035a429fe23a)
    $ ecs-tank drain sfr-fca68ac3-cc9b-4bb9-902b-e0114daeeb10 --cluster development
    Finding ECS instances associated spot fleet: sfr-fca68ac3-cc9b-4bb9-902b-e0114daeeb10
    Spot instance ids:
    i-08cd804e917f595c2
    i-0d149035a429fe23a
    Updating container instances with status DRAINING:
    1a4ece6726304582bdc89dfe0e6ce849 (i-0d149035a429fe23a)
    1b87e6aef6804d3483f1d71c864e02a4 (i-08cd804e917f595c2)
    $ ecs-tank drain ecs-asg-Asg-1BN0X6P9RH5OK --cluster development
    Finding ECS instances associated autoscaling group: ecs-asg-Asg-1BN0X6P9RH5OK
    EC2 Instances:
    i-0815a4cfece69d3d3
    Updating container instances with status DRAINING:
    dfd50aefbf9a4819aa5589297da549a2 (i-0815a4cfece69d3d3)

Fill commands:

    $ ecs-tank fill i-0d149035a429fe23a --cluster development
    Finding Instance: i-0d149035a429fe23a
    Updating container instances with status ACTIVE:
    1a4ece6726304582bdc89dfe0e6ce849 (i-0d149035a429fe23a)
    $ ecs-tank fill sfr-fca68ac3-cc9b-4bb9-902b-e0114daeeb10 --cluster development
    Finding ECS instances associated spot fleet: sfr-fca68ac3-cc9b-4bb9-902b-e0114daeeb10
    Spot instance ids:
    i-08cd804e917f595c2
    i-0d149035a429fe23a
    Updating container instances with status ACTIVE:
    1a4ece6726304582bdc89dfe0e6ce849 (i-0d149035a429fe23a)
    1b87e6aef6804d3483f1d71c864e02a4 (i-08cd804e917f595c2)
    $ ecs-tank fill ecs-asg-Asg-1BN0X6P9RH5OK --cluster development
    Finding ECS instances associated autoscaling group: ecs-asg-Asg-1BN0X6P9RH5OK
    EC2 Instances:
    i-0815a4cfece69d3d3
    Updating container instances with status ACTIVE:
    dfd50aefbf9a4819aa5589297da549a2 (i-0815a4cfece69d3d3)
    $

List commands:

    $ ecs-tank list development
    +---------------------+----------------------------------+--------+
    |     Instance Id     |      Container Instance Id       | Status |
    +---------------------+----------------------------------+--------+
    | i-0ec7fb3706d612fdb | 442ea5029df446ec94f0262d8856ce1f | ACTIVE |
    | i-0e30fca4a5b1fc974 | 4bf71221195847c5bd8cbbeac4e1d673 | ACTIVE |
    +---------------------+----------------------------------+--------+
    $

## Go Back to Reference Architecture

That's it. Go back to the main [boltopspro/reference-architecture](https://github.com/boltopspro-docs/reference-architecture/blob/master/README.md)
