# An AI for Rocket League that balances the ball on its car

The objective of the project was to implement PID loops to keep the ball centered on the car.
It also contains code telling the bot how to approach the ball to guarantee a good start.
Finally WASD controlls were added that tell the bot to offset the position of the ball on the car, causing the ball to accelerate forwards, backward, left, or right.

## Installation

The project is based in RLBot, found here: https://github.com/RLBot/RLBot
To use, install RLBot, open Rocket League to the main menu, and run the "run.bat" file

## PID Controllers

PID stands for Proportional Integral Derivitive, and denotes the three factors that maintain a self stabalizing system.  The proportional (P) term is the distance the ball is from the car, the derivitive (D) is the change in distance over time, the integral (I) would be the accumulated error over time, but since Rocket League is a  physics engine and not a real world system, we can ignore error.
Instead we use the speed of the ball as the final term, such that the ball doesn't accelerate out of control.  (Side note: since the ball is accelerated by its offset on the car, this term is actually an approximation of the integral.)

The factors in front of the P and D terms, as well as the speed of the ball, are adjusted until the bot can position itself under the ball quickly and with minimal overshoot.  We can also introduce bias terms so that the ball is balanced on the side of the car, allowing it to turn, or biases in the desired speed of the ball.  These biases are controlled by the user using WASD.

## Demonstration

The following video shows the bot dribbling.  Most of the time "A" or "D" is being held on the keyboard, causing the ball to be offset and the ball and the bot to turn.

[![Dribble Bot](http://i.imgur.com/Gf9AH3Q.jpg)](https://youtu.be/3pKObZwQ5xU "Dribble Bot")

## Special thanks

To the Dev team behind RLBot and their tutorials!  They have a Reddit and Discord and welcome new users: https://www.reddit.com/r/RocketLeagueBots/
This project uses the same base code found in their basic tutorial:
https://github.com/RLBot/RLBotPythonExample
