LinearOpMode vs OpMode
======================

There are two OpMode classes within the FTC SDK: ``OpMode`` and ``LinearOpMode``. The one you use affects how you write the program. For examples of how to use OpMode and LinearOpMode, `refer to the example OpModes in the SDK <https://github.com/FIRST-Tech-Challenge/FtcRobotController/tree/master/FtcRobotController/src/main/java/org/firstinspires/ftc/robotcontroller/external/samples>`_.

LinearOpMode Methods
--------------------

.. note:: LinearOpMode is generally preferred due to OpMode inserting 5 ms delays if the user's loop takes less than 1 ms as well as being prone to random delays.

- ``runOpMode()``: Code inside this method will run exactly once after you press the INIT button. This is where you should put all code for the OpMode.
- ``waitForStart()``: This method pauses the Op-Mode until you press the START button on the driver station.
- ``isStarted()``: returns ``true`` if the START button has been pressed, otherwise it returns ``false``.
- ``isStopRequested()``: returns ``true`` if the STOP button has been pressed, otherwise it returns ``false``.
- ``idle()``: calls ``Thread.yield``, allowing other threads at the same priority level to run.
- ``opModeIsActive()``: returns ``isStarted() && !isStopRequested()`` and calls ``idle()``.
- ``opModeInInit()``: returns ``!isStarted() && !isStopRequested()`` and does not call ``idle()``.

OpMode Methods
^^^^^^^^^^^^^^

- ``init()``: Code inside this method will run exactly once after you press the INIT button on the driver station.
- ``init_loop()``: Once the code in ``init()`` has been run, code inside this method will run continuously until the START button is pressed on the driver station.
- ``start()``: Code inside this method will run exactly once after you press the START button on the driver station.
- ``loop()``: Once the code in ``start()`` has been run, code inside this method will run continuously until the STOP button is pressed on the driver station.
- ``stop()``: Code inside this method will run exactly once after you press the STOP button on the driver station.

