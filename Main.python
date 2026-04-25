from kipr import *

# Motor port numbers - change these to match your wiring
LEFT_MOTOR = 3
RIGHT_MOTOR = 0

CLAW_SERVO = 0     # change to your actual port
ARM_SERVO = 1      # if you also have an arm that lifts

CLAW_OPEN = 1800
CLAW_CLOSED = 500
ARM_UP = 1500
ARM_DOWN = 500

BLACK = 4000  # adjust this value - lower number = more light, higher = more dark


def move_forward(SPEED, DURATION):
    DURATION = int(DURATION * 1000)  # turn into seconds
    motor(LEFT_MOTOR, SPEED)
    motor(RIGHT_MOTOR, SPEED)
    msleep(DURATION)
    ao()


def move_back(SPEED, DURATION):
    DURATION = int(DURATION * 1000)
    motor(LEFT_MOTOR, -SPEED)
    motor(RIGHT_MOTOR, -SPEED)
    msleep(DURATION)
    ao()


def turn_right(degree):
    motor(LEFT_MOTOR, -100)
    motor(RIGHT_MOTOR, 100)
    time = int(900 * degree / 90)
    msleep(time)


def turn_left(degree):
    motor(LEFT_MOTOR, 100)
    motor(RIGHT_MOTOR, -100)
    time = int(900 * degree / 90)
    msleep(time)


def move_forward_until_black():
    motor(LEFT_MOTOR, 50)
    motor(RIGHT_MOTOR, 50)
    while analog(1) < BLACK:
        msleep(10)


def open_claw():
    set_servo_position(CLAW_SERVO, CLAW_OPEN)
    msleep(500)


def close_claw():
    set_servo_position(CLAW_SERVO, CLAW_CLOSED)
    msleep(500)


def move_claw_up():
    set_servo_position(ARM_SERVO, ARM_UP)
    msleep(500)


def move_claw_down():
    set_servo_position(ARM_SERVO, ARM_DOWN)
    msleep(500)


def main():
    motor(2, 50)
    enable_servos()
    open_claw()
    move_claw_down()
    close_claw()
    move_claw_up()
    print("done")


if __name__ == "__main__":
    main()
