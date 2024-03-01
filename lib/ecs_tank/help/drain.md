<!-- note marker start -->
NOTE: This repo contains only the documentation for the private BoltsOps repo code.
Original file: https://github.com/boltops-pro/ecs-tank/blob/master/lib/ecs_tank/help/drain.md
The docs are publish so they are available for interested subscribers.
For access to the source code, you can become a BoltOps subscriber.
See: https://learn.boltops.com

<!-- note marker end -->

## Examples

    ecs-tank drain i-0d149035a429fe23a --cluster development
    ecs-tank drain sfr-fca68ac3-cc9b-4bb9-902b-e0114daeeb10 --cluster development
    ecs-tank drain ecs-asg-Asg-1AAPTSUCCP4RH
    ecs-tank drain ecs-asg-Asg-1AAPTSUCCP4RH --cluster development
    ecs-tank drain ecs-asg-Asg-1AAPTSUCCP4RH --cluster development --noop
