<!-- note marker start -->
**NOTE**: This repo contains only the documentation for the private BoltsOps Pro repo code.
Original file: https://github.com/boltopspro/ecs-tank/blob/master/lib/ecs_tank/help/completion.md
The docs are publish so they are available for interested customers.
For access to the source code, you must be a paying BoltOps Pro subscriber.
If are interested, you can contact us at contact@boltops.com or https://www.boltops.com

<!-- note marker end -->

## Examples

    ecs-tank completion

Prints words for TAB auto-completion.

    ecs-tank completion
    ecs-tank completion hello
    ecs-tank completion hello name

To enable, TAB auto-completion add the following to your profile:

    eval $(ecs-tank completion_script)

Auto-completion example usage:

    ecs-tank [TAB]
    ecs-tank hello [TAB]
    ecs-tank hello name [TAB]
    ecs-tank hello name --[TAB]
