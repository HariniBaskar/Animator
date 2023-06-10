# Animator

## Aim:
To develop an animator that changes it's movement using C# program in Unity.

## Algorithm:
### Step 1: 
Download 2 crouch idle from maximo 3d. Drag it and drop it in unity asset.
### Step 2: 
Select one crouch and in the inspector choose rig-> Animation type (humaniod) and then click update.
### Step 3: 
Perform the step 2 for another crouch
### Step 4: 
Select one crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 5: 
Perform the step 4 for another crouch
### Step 6: 
Drag one crouch, put it in hierarchy and name it as Player.
### Step 7: 
In the Player inspector we have Animator. Right click in Assets-> create -> Animator Controller (name it as IdleToCrouch)
### Step 8: 
Drag the IdleToCrouch to the Controller option under the Animator in the inspector. Click that IdleToCrouch , a window opens and select parameter tab , create 2 parameter, InputX and InputY
### Step 9: 
Select the another crouch and attach with Entry button and name it as movement. Right click it and choose create blend tree.
### Step 10: 
Click the movement button, blend tree opens. Choose InputY in parameter and under the motion click ‘+’ sign and choose add the motion field twice.
### Step 11: 
Drag the second crouch and put it motion field, then drag the first crouch and put it in the another motion field.
### Step 12: 
Uncheck the automata threshold and change the values -1 and 0 in first column( priority for the crouch). Create a C# file and name it as IdleToCrouch, drag it to the player
### Step 13: 
Download a walking crouch from maximo 3d and drag it into unity. In the inspector select rig-> animation types(humanoid) -> Apply
### Step 14: 
Select the crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 15: 
In blend tree, in blend type choose (2D Freedom Directional), parameter (InputX, InputY) , one crouch (0,-1,1) and walking (1,0,1). Bring the camera under the player 

## Program:
```
Developed By: Harini.B
Register Number: 212221230035
```
### IDLE TO CROUCH:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class IdletoCrouch : MonoBehaviour
{
    public Animator animator;
    public float InputX;
    public float InputY;
    // Start is called before the first frame update
    void Start()
    {
        animator = this.gameObject.GetComponent<Animator>();
        
    }

    // Update is called once per frame
    void Update()
    {
        InputX = Input.GetAxis("Vertical");
        InputY = Input.GetAxis("Horizontal");
        animator.SetFloat("InputX", InputX);
        animator.SetFloat("InputY", InputY);
    }
}
```
## Output:
![out611](https://github.com/HariniBaskar/Animator/assets/93427253/65fcbccb-6a23-490b-8a9b-3acfbd41a639)

![out62](https://github.com/HariniBaskar/Animator/assets/93427253/1ad54f85-a5f4-4280-b979-3a365268b660)


## Result:
Thus, an animator that changes it's movement using C# program in Unity engine is developed and executed successfully.
