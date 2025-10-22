# Ex4.2-Animal-Feeding-Phase-2
# Name: HARISELVAN S
## Reg no: 212224040103
## Aim:
To develop a animal feeding game-Phase-2 using unity.
## Algorithm:
## Step 1:
In the Hierarchy, create an Empty object called “SpawnManager”

## Step 2:
Create a new script called “SpawnManager”, drag the script and attach it to the Spawn Manager in the hierarchy , and open it

## Step 3:
Declare new public GameObject[ ] animalPrefabs;

## Step 4:
In the inspector assign the size as 3 , for each element drag the animals from prefabs folder into the array

## Step 5:
Double-click on one of the animal prefabs, then Add Component > Box Collider

## Step 6:
Check the “Is Trigger” checkbox

## Step 7:
Add a RigidBody component to the (banana)projectile and uncheck “use gravity”.

## Step 8:
Create a new DetectCollisions.cs script, then drag the scripts and add it to each animal prefab and banana, then open it and check it.

## Step 9:
For all the animal prefabs and food in th inspector (below the layer ) drop down the override option and choose apply all.
## Program:
# Spawn Manager:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpawnManager : MonoBehaviour
{
    public GameObject[] animalPrefabs;
    private float spawnRangeX = 1;
    private float spawnPosZ = 1;
    private float startDelay = 2f;
    private float spawnInterval = 1.5f;

    void Start()
    {
        InvokeRepeating("SpawnRandomAnimal", startDelay, spawnInterval);
    }

    // Update is called once per frame
    void Update()
    {

    }

    void SpawnRandomAnimal()
    {
        int animalIndex = Random.Range(0, animalPrefabs.Length);
        Vector3 spawnPos = new Vector3(Random.Range(-spawnRangeX, spawnRangeX), 0, spawnPosZ);
        Instantiate(animalPrefabs[animalIndex], spawnPos, animalPrefabs[animalIndex].transform.rotation);
    }
}
```

# Detect Collider:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DetectCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {

    }
    private void OnTriggerEnter(Collider other)
    {
        Destroy(other);
        
    }
}

```
## Output:
<img width="1914" height="939" alt="image" src="https://github.com/user-attachments/assets/ddc21a83-da6f-4db0-8b40-1350bbd46298" />

## Result:
Thus,Animal feeding game-Phase-2 using unity is developed successfully.
