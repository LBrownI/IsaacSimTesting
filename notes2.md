US-01 — Launch the simulator with a predefined scene #1

As a simulation user, I want to start Isaac Sim and automatically load the base simulation scene, so that I do not need to manually assemble the environment each time.
Acceptance Criteria

    Isaac Sim starts with one command or launcher entry.
    The base scene loads automatically.
    The world contains the robot root, environment root, and physics configuration.
    No manual dragging or scene editing is required to reach the initial state.


US-02 — Load the UR5 robot into the simulation #2

As a robotics engineer, I want the simulator to load a UR5 robot model, so that I can use it as the main manipulator in the industrial process simulation.
Acceptance Criteria

    The UR5 appears in the scene at the configured base pose.
    The robot is loaded as a valid articulated robot.
    All expected joints are available and controllable.
    The robot can be reset to a default joint configuration.


US-03 — Define the robot initial position and default configuration #3

As a simulation developer, I want the UR5 to start from a known base pose and joint configuration, so that every simulation run begins from a repeatable state.
Acceptance Criteria

    The robot base position and orientation can be configured.
    Default joint angles are defined in configuration.
    Resetting the simulation restores the same initial state.


US-04 — Load industrial environment elements from STL files #4

As a simulation engineer, I want to load environment components from multiple STL files, so that the simulated cell represents the real industrial setup.
Acceptance Criteria

    The simulator can load multiple STL files from a configured folder or list.
    Each STL becomes a named object in the scene.
    STL loading works without manual import steps inside Isaac Sim.

US-05 — Configure pose and scale of each environment object #5

As a simulation engineer, I want to define the position, rotation, and scale of each imported STL object, so that each industrial asset appears in the correct location.
Acceptance Criteria

    Every STL object can be configured with translation, rotation, and scale.
    The final scene layout matches the defined configuration.
    Updating the config changes the scene without code changes.


US-06 — Enable collision for environment objects #6

As a robot programmer, I want environment objects to have collision geometry, so that the robot can be tested safely in a realistic workspace.
Acceptance Criteria

    Each relevant STL object has collision enabled.
    Collision approximation mode can be defined per object.
    The robot cannot pass through collision-enabled environment assets.


US-07 — Mark static environment assets as fixed #7

As a simulation engineer, I want the imported industrial assets to behave as static objects, so that the robot moves around a stable workspace.
Acceptance Criteria

    Static assets are not affected by gravity or robot contact.
    Objects such as tables, guards, and machines remain fixed during simulation.
    Static/dynamic behavior is configurable per object.



US-08 — Attach a camera to the robot end effector #8

As a robotics developer, I want a camera mounted on the robot end effector, so that I can simulate wrist-mounted visual inspection or guidance.
Acceptance Criteria

    A camera is attached to the UR5 end-effector frame.
    The camera moves with the robot during motion.
    The relative pose of the camera with respect to the end effector is configurable.



US-09 — Configure camera parameters #9

As a vision engineer, I want to configure the camera resolution, frame rate, and frame ID, so that the simulated camera matches the expected use case.
Acceptance Criteria

    Resolution can be configured.
    Publish/update frequency can be configured.
    Camera frame name is defined and exposed consistently.


US-10 — Publish camera data externally through ROS #10

As a robotics integrator, I want the end-effector camera to publish image topics through ROS, so that external applications can consume the simulated camera feed.
Acceptance Criteria

    RGB image topic is published.
    Camera info topic is published.
    Frame ID is correct.
    Topic names are documented and stable.



US-11 — Expose the robot for external control #11

As a robotics integrator, I want the robot to be controllable from external software, so that the simulator can be used together with planning and programming tools.
Acceptance Criteria

    External commands can move the robot in simulation.
    Robot state is available outside the simulator.
    The control interface is documented.



US-12 — Support ROS-based robot control #12

As a ROS user, I want to control the robot through ROS interfaces, so that I can integrate Isaac Sim with ROS-based tooling.
Acceptance Criteria

    Joint states are published to ROS.
    The simulator subscribes to robot command topics.
    Sending a valid joint command changes the robot state in simulation.
    Topic names and message types are documented.



US-13 — Support MoveIt as an external planner/controller path #13

As a motion planning engineer, I want to use MoveIt to plan and send motions to the simulated UR5, so that I can validate motion planning against the virtual workcell.
Acceptance Criteria

    The simulator can receive commands from a ROS/MoveIt workflow.
    A basic MoveIt execution example is provided.
    The UR5 follows a simple planned motion in the simulator.



US-14 — Support RoboDK as an external programming path #14

As a robot programmer, I want to connect RoboDK or similar software to the simulator, so that I can use offline programming tools with the virtual cell.
Acceptance Criteria

    The simulator design allows external connection from RoboDK.
    A simple RoboDK demonstration workflow is documented.
    A robot program created externally can be reflected in the simulation.



US-15 — Keep simulator setup in configuration files #15

As a simulation maintainer, I want robot, camera, and environment setup to be stored in configuration files, so that the scene can be changed without rewriting the simulator logic.
Acceptance Criteria

    Robot source, scene objects, and camera settings are defined in configuration.
    Environment asset paths are configurable.
    External interface settings are configurable.
    A user can update the scene by editing config values.



US-16 — Separate scene loading from interface setup #16

As a developer, I want the scene assembly and external interfaces to be modular, so that the system is easier to extend in future iterations.
Acceptance Criteria

    Robot loading is implemented independently from environment loading.
    Camera attachment is implemented independently from robot loading.
    ROS/RoboDK setup is implemented independently from scene construction.



US-17 — Provide a simple ROS usage example #17

As a new user of the simulator, I want a minimal ROS example showing how to command the robot, so that I can quickly verify the integration works.
Acceptance Criteria

    An example script or command sequence is provided.
    The example sends a simple joint-space motion.
    The robot moves in Isaac Sim when the example is run.
    Required topics and steps are documented.



US-18 — Provide a simple camera usage example in ROS #18

As a ROS developer, I want an example showing how to subscribe to the robot camera topics, so that I can verify the sensor integration works.
Acceptance Criteria

    The example shows how to view or subscribe to the camera feed.
    The example references the correct image and camera info topics.
    The example works with the mounted end-effector camera.



US-19 — Provide a simple RoboDK usage example #19

As a RoboDK user, I want a minimal example showing how to connect RoboDK with the simulation, so that I can test external robot programming against Isaac Sim.
Acceptance Criteria

    The example includes the connection assumptions.
    The example demonstrates one simple motion or synchronization workflow.
    The expected result in Isaac Sim is described clearly.



US-20 — Verify the base simulator is ready for future iterations #20

As a project owner, I want clear validation criteria for the first iteration, so that I know when the base simulator is complete and ready to extend.
Acceptance Criteria

    UR5 loads correctly.
    At least the required STL environment objects load correctly.
    The camera is mounted and moves with the end effector.
    ROS control works with a simple command example.
    A basic RoboDK workflow is documented.
    The scene can be launched repeatably from configuration.

