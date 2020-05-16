# Understanding ROS 2 actions
> Actions are one of the communication types in ROS 2 intended for long running tasks.
> They consist of three parts: a goal, a result, and a feedback.
> Actions are built on topics and services. Their functionality is similar to services,
> except actions are preemptable(you can cancel them while executing).
> They also provide steady feedback, as opposed to services which return a single response.
> Actions use a client-server model, similar to the publisher-subscriber model. The
> "action client" node sends a goal to an "action server" node that acknowledge the goal
> and returns a stream of feedback and a result.
