# EraScript Documentation

## Functions
- ```js
  UObject* findObject("Object", false)
  ```
  Finds an UObject by name. The second argument decides whether the name has to be exact
  - Usage:
    ```js
    var object = findObject("BlueprintGeneratedClass HuskPawn");
    ```
    ```js
    var object = findObject("BlueprintGeneratedClass HuskPawn.HuskPawn_C", true);
    ```
- ```js
  String getObjectName(Object)
  ```
  Returns the name of an object
  - Usage:
    ```js
    var object = findObject("FortWeaponRangedItemDefinition WID_Sniper_Crossbow_Athena_R_Ore_T03");
    console.log(getObjectName(object));
    // FortWeaponRangedItemDefinition WID_Sniper_Crossbow_Athena_R_Ore_T03.WID_Sniper_Crossbow_Athena_R_Ore_T03
    ```
- ```js
  FVector getLocation(Actor)
  ```
  Returns the location of an Actor
  - Usage:
    ```js
    console.log(getLocation(getLocalPlayer()));
    // {X:-124119.125,Y:-116151.125,Z:3917.18408203125}
    ```
- ```js
  spawnActor(Object, FVector)
  ```
  Spawns an Actor
  - Usage:
    ```js
    var object = findObject("BlueprintGeneratedClass HuskPawn");
    spawnActor(object, new FVector(0, 0, 0));
    ```
- ```js
  destroyActor(Actor)
  ```
  Destroys an Actor
  - Usage:
    ```js
    var object = findObject("BlueprintGeneratedClass HuskPawn");
    var husk = spawnActor(object, new FVector(0, 0, 0));
    
    messageBox("Press OK to destroy the husk.");
    destroyActor(husk);
    ```
- ```js
  Array<UObject*> findActorsOfClass(Object)
  UObject* findActorsOfClass(Object, 0)
  ```
  Finds all/one Actor of a class
  - Usage:
    ```js
    var object = findObject("BlueprintGeneratedClass HuskPawn");
    spawnActor(object, new FVector(0, 0, 0));
    
    console.log(findActorsOfClass(object));
    ```
- ```js
  executeConsoleCommand("command")
  ```
  Executes a console command
  - Usage:
    ```js
    executeConsoleCommand("demospeed 2");
    ```
- ```js
  teleport(Actor, FVector)
  ```
  Teleports an Actor
  - Usage:
    ```js
    teleport(getLocalPlayer(), new FVector(0, 0, 0));
    ```
- ```js
  messageBox("Message")
  ```
  Shows a message box
  - Usage:
    ```js
    messageBox("Hello, World!")
    ```
- ```js
  playSound(Sound, FVector, Volume, Pitch)
  ```
  Plays a sound
  - Usage:
    ```js
    var sound = findObject("SoundCue airstrike_incoming_place_Cue");

    playSound(sound, getLocation(getLocalPlayer()), 1 ,1);
    ```
- ```js
  spawnPickup(Object, FVector, 1)
  ```
- ```js
  grantAbility(Object)
  ```
- ```js
  addToInventory(Object, 1)
  ```
- ```js
  bool isInVehicle()
  ```
- ```js
  UObject* getVehicle()
  ```
- ```js
  setScaleActor(Actor, FVector)
  ```

## Classes
- **FVector**
  ```js
  new FVector(0, 0, 0)
  ```
- **FRotator**
  ```js
  new FRotator(0, 0, 0)
  ```
- **TArray<T>**
  Only used in the global variables. Only reading the TArrays is allowed currently
  - ```js
    T TArray.get(1)
    ```
    ```js
    Array<T> TArray.get()
    ```
    Returns the TArray item at the index or all of the items if no arguments are passed.
  - ```js
    TArray.length
    ```
    Returns the length of the TArray

## Global Variables
- TArray<int> **ammoItemCount**
- TArray<UObject*> **ammoItemDefs**
- TArray<int> **consumablesItemCount**
- TArray<UObject*> **consumablesItemDefs**
- TArray<int> **resourceItemCount**
- TArray<UObject*> **resourceItemDefs**
- TArray<int> **trapsItemCount**
- TArray<UObject*> **trapsItemDefs**
- TArray<int> **weaponItemCount**
- TArray<UObject*> **weaponItemDefs**
- TArray<int> **resourceItemCount**
- TArray<UObject*> **resourceItemDefs**
- String **fortniteVersion**
