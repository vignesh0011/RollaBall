# RollaBall

## Aim:
To Roll a Ball using C# program in unity .

## Algorithm:

1. File -> Scene -> Select the scene -> Save as-> New folder(Scenes)-> File name (MiniGame)

2. Heirarchy -> 3D Object-> Plane 
[ Right side-> Inspector-> Change the name of plane (Name: Ground)
Transform -> Reset
Edit -> FrameSelected ]

3. Scale the ground by giving the scaling value as x=4 y=1 z=4

4. Heirarchy -> 3D Object-> Sphere
[ Right side-> Inspector-> Change the name of plane (Name: Player)
Transform -> Reset
Edit -> FrameSelected 
Transform -> Position -> y=0.5]

5. Hierarchy -> DirectionalLight
[ Inspector -> Change the color to white (255,255,255)]

6. Create a folder in project and name as Materials
[Material folder -> Create -> Material (Name: Background)
Inspector ->Surface Inputs ->BaseMAp (Choose the color)
Metallic map-> 0
Smoothness -> 0.25
Drag the Background to the plane and release the mouse

Material folder -> Create -> Material (Name: Sphere)
Inspector ->Surface Inputs ->BaseMAp (Choose the color)
Metallic map-> 0
Smoothness -> 0.75
Drag the Sphere material to the ball and release the mouse

 7. Hierarchy -> Player-> Inspector ->Add component-> Rigidbody

8. Create a new script -> Create a folder in project (Name: Scripts)
Hierarchy -> Player -> Inspector-> AddComponent-> NewScripts-> PlayerController( Click create and Add)
Copy the PlayerController and drag to Script folder
Double click the PlayerController file and type the coding

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Object1 : MonoBehaviour
{
    // Start is called before the first frame update
    public float xmove = 7.0f;
    public float zmove = 5.0f;
    public float ymove = 150.0f;
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        float x = 0.0f;
        if(Input.GetKey(KeyCode.UpArrow))
        {
            x += xmove;
        }
        if(Input.GetKey(KeyCode.DownArrow))
        {
            x -= xmove;
        }
        float z = 0.0f;
        if(Input.GetKey(KeyCode.RightArrow))
        {
            z -= zmove;
        }
        if(Input.GetKey(KeyCode.LeftArrow))
        {
            z += zmove;
        }
        float y = 0.0f;
        if(Input.GetKeyDown(KeyCode.Space))
        {
            y = ymove;
        }
        GetComponent<Rigidbody>().AddForce(x, y, z);
    }
}
```

## Output:
![image](https://github.com/vignesh0011/RollaBall/assets/53014593/707020d7-0c40-418e-a5cf-434484b715da)


![image](https://github.com/vignesh0011/RollaBall/assets/53014593/f5f7ff4f-067c-4669-b057-cb432c600fc0)


## Result:
Thus, The 3D application for Roll the Ball objects in unity is developed successfully.
