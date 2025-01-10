# 3DUnityJumpMechanicTutorial
A tutorial on how to program a jumping mechanic in a 3D Unity environment using C#.

This tutorial follows on from the first person movement tutorial.

This tutorial follows on from the First Person Camera Tutorial.

1. Navigate to your script that controls your players movement.

2. We will first want to declare our variables. We will need: public float jumpForce (public float variable to store the value for the jump force); public float jumpCoolDown (set a timer on a the jump cooldown so that it isn't spammable); public float air multiplier (so speed is slowed while airborne); bool readyToJump (boolean variable so we know whem the jumpCoolDown hits 0, readyToJump will be true); public float playerHeight (will be used for the ground check); public LayerMask whatIsGround (so that the ground is on it's on layer that the raycast from our player can detect for the ground check); bool grounded (boolean variable so we know if the player is in contact with the ground); Rigidbody rb (the rigid body component from our player); public float groundDrag (for more realistic movement).

3. Firstly we will need to perform a raycast from our players position to the ground. We will do this in the update method so the raycast in constant.

![image](https://github.com/user-attachments/assets/25217bb5-ac39-4da9-8789-452715f75c62)
 
   
