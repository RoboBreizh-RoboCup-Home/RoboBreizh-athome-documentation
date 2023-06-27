# Preparation day

- Mesure room
- Draw the map using the measurements
- Test navigation parameters using nav goal
- Set location points

## Few shots instructions

- 30 classes
- 300 images
- split by clusters
- 6 - 8 objects per cluster
- only table is enough but if more time more environments (shelf etc..)
- 3 images per scene (1 scene = 1 cluster in 1 position, i.e. we don’t move the objects in between images)
- shuffle half of the cluster + change position of objects →new scene 
- for the pictures: 1 from above + 2-3 different angles from the side, make sure objects touch edge of the picture
- annotate on roboflow
- DO NOT CREATE A TEST SET
- export to YOLO format

AIM: 30-40 instances per class, 40*30 classes = 1200 instances = 1200 bounding boxes annotated

