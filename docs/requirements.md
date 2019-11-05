# Requirements Definitions

* Arm control -> physical control
* Human interface (input) -> control input
* Display output -> Output display
* Locomotion driving -> physical control
* Fault tolerance -> Fault tolerance
* Cope with N motors/hardware devices -> physical control
* Telemetry -> T&T
* Telecommand -> T&T
* Autonomy -> <!-- TODO -->
* logging tests <!-- TODO -->

## Output display

* Graphical User Interface
* Video display of rover's camera
* Representation of rover's internal sate
  * arm
  * wheels
* Show user input of user
  * compare input to output
* Rover external
  * speed
  * location
  * heading
  * orientation (absolute 3D rotation)
  
## Physical control

* Control the electronics
* Mathematic/Kinematic model of the...
  * rover wheels
  * arm
  * input to output mapping
* End effector control
* Report back
  * motor signal given
  * arm positions
  * wheel speeds issued
  
## Control input

* Take input from control mechanism
* Intuitive / Training the person
* _Many_ simultaneous hardware devices
* map raw input to general abstract high level input
  * profiles / invert controls for user
* transmit
* report actual transmission

## Fault tolerance

* modularity: little interdependænce
* Detect fault
  * making sure external data sources are inline with internal state
  * e.g if suddenly on jupiter, you're not on jupiter, the accelerometer's gone funny
* isolate
  * raise exception, signal untrustworthy data
  * e.g. if suddenly on jupiter, tell dependants not to trust this data
* patch
  * individual systems deciding how to act when SoD (suddenly on Deimos)
* recover
  * don't explode I guess?

## Telecommand & Telemetry

* talk with other (software) components
  * hardware standard
  * protocol standard
* defined topology
* module interface
* issue commands/data from network
* put commands/data on network
* __L A T E N C Y__ awareness/generally not having much

## Autonomy

* issue high-level commands
* work
* __M A K E   D E C I S I O N S__
