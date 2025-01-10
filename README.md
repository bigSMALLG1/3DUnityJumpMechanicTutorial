# 3DUnityJumpMechanicTutorial
A tutorial on how to program a jumping mechanic in a 3D Unity environment using C#.


This tutorial follows on from the first person movement tutorial!


1. Navigate to your script that controls your players movement.

2. We will first want to declare our variables. We will need: public float jumpForce (public float variable to store the value for the jump force); public float jumpCoolDown (set a timer on a the jump cooldown so that it isn't spammable); public float air multiplier (so speed is slowed while airborne); bool readyToJump (boolean variable so we know whem the jumpCoolDown hits 0, readyToJump will be true); public float playerHeight (will be used for the ground check); public LayerMask whatIsGround (so that the ground is on it's on layer that the raycast from our player can detect for the ground check); bool grounded (boolean variable so we know if the player is in contact with the ground); Rigidbody rb (the rigid body component from our player); public float groundDrag (for more realistic movement).

3. Firstly we will need to perform a raycast from our players position to the ground. We will do this in the update method so the raycast in constant.

![image](https://github.com/user-attachments/assets/25217bb5-ac39-4da9-8789-452715f75c62)

Our players height is 1 so the raycast will be half of our players height so it's 0.5f.

4. Go back in to unity and create a new layer called whatIsGround and assign your ground to that layer.

![image](https://github.com/user-attachments/assets/07309ceb-4169-46e0-aa26-752cab6209eb)

![image](https://github.com/user-attachments/assets/dca8998e-ce00-4b79-b3b1-f2c4235209b1)

5. You now have a functional raycast for the ground check which we will use for jumping.

6. Create a new function called Jump private void Jump()
{
}

![image](https://github.com/user-attachments/assets/89248dcc-c93d-4b34-8137-598e0feae0ee)

set the y velocity to 0 so that your player jumps the same height each time

![image](https://github.com/user-attachments/assets/b391f64a-49ee-4c1b-aabc-a93f1f1fcf93)

7. Next we want to add the force of jumping upwards to our player. We will do this by using rb.AddForce which adds a force to the rigidbody on our player. The paramters being transform.up for the forces direction. This is multiplied by our jumpForce to determine how much force is in our jump. We will also use ForceMode.Impulse as we are only doing this once when the jump key is pressed, rather than this force being constant.
   
9. Then make a ResetJump function to set readyToJump to true again once the player is grounded. We will need to assign the jumpkey to the spacebar so type public (KeyCode jumpKey = KeyCode.Space;) where your other variables are. 
 
 
   
![image](https://github.com/user-attachments/assets/66932d27-dfc9-41ad-a53d-79d04dd39695)

10. Navigate back to your KeyInput method where we will be using an if statement for when the spacebar is pressed depending on whether the player is ready to jump and is grounded.
 
![image](https://github.com/user-attachments/assets/68a43f07-b5ef-415a-9f26-555a42c7a0e3)


Inside the if statement we want to set readyToJump as false because we will have already pressed the spacebar and will be in the midst of jumping so we don't want to be able to jump again. We also call the Jump method so we can actually jump and then we invoke the ResetJump method and start the cooldown so we can jump again when ready.

11. Finally, add these if and else if statements so we can apply the air multiplier and have better air control when jumping.

12. Go back in to unity and change the values of the JumpForce and, JumpCoolDown and AirMultiplier to your liking.



 
   
