# Roadmap

---

## Concepts

### Navigation

- [x] Navigation with obstacle ovoidance (Dikjstra, DWA/TEB, AMCL)
- [ ] Visual SLAM solution

### Perception

- [ ] Person tracking
- [ ] YCB training
- [x] Color detection (K-mean)
- [x] Detect human pose (multipose)
- [x] Detect door state open/close (NAOqi sonar)
- [x] Detect features of a person (COCO, OID)
- [x] Face detection (COCO, OID)
- [x] Detect objects (COCO, OID)
- [x] Detect seat states free/taken (COCO, OID)

### Manipulation

- [ ] Execute grasp
- [ ] Plan grasp (avoid obstacles)
- [ ] Compute grasp position

### Dialog

- [x] Text to speech (NAOqi TTS api)
- [x] Natural Language Processing (Vosk)
- [x] Speech recognition
- [x] Speech detection

---

## Tasks

Here is the list of stuff to do regarding the different tasks

### Carry my luggage

- [ ] During navigation avoid a small object, crowd, a hard to see object and a barrier
- [ ] Bag detection
- [ ] [VisionFindObjectPointedByHuman](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper/blob/76a612f6fcbf469d944ff2befdbe2be1545cfc0e/src/plan_high_level_actions/vision_plan_actions.cpp#L409-L432)
- [ ] [NavigateMoveTowardsObject](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper/blob/54b3253cf098748e50215ca1933cfa24f001bd2e/src/plan_high_level_actions/navigation_plan_actions.cpp#L25-L38)
- [ ] [ManipulationBendArms](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper/blob/54b3253cf098748e50215ca1933cfa24f001bd2e/src/plan_high_level_actions/gesture_plan_actions.cpp#L59-L72)
- [ ] [FollowHuman](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper/blob/54b3253cf098748e50215ca1933cfa24f001bd2e/src/plan_high_level_actions/navigation_plan_actions.cpp#L40-L46)
- [ ] Lack of recovery behaviour when looking for someone

### Receptionist

- [ ] Pose detection is not accurate, test it with the scenario
- [ ] Age detection is not accurate, test it with the scenario

### Storing groceries

- [ ] Feedback if the destination is missing
- [ ] Init function doesn't reset the variable "param_number_of_guests_welcomes" (variable name is unrelated to the scenario). This prevent tests to be done.
- [ ] Navigation times out
- [ ] Shelf detection is not implemented

### Serve breakfast

- [ ] Init function missing

### GPSR

- Not testing until the NLP is done

### Clean the table

- [ ] Init function missing

### Restaurant

- [ ] NavigationMoveTowardsHuman_nextCustomer not implemented
- [ ] Error with unsuccessful tries variable

### Stickler for the rules

- [ ] Update coordinates for the forbidden room
- [ ] Implement other rules

### EGPSR
