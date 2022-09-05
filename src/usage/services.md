# Services

- [Services](#services)
  - [Perception](#perception)
  - [Navigation](#navigation)

## Perception

| Function    | Service |
| ----------- | ----------- |
| All objects | /robobreizh/perception_pepper/object_detection_service "{entries_list:[data: 'ALL']}"|
| Person and char | /robobreizh/perception_pepper/object_detection_service "{entries_list: [data : "person", data : "chair"] }" |
| Human features with distance |  /robobreizh/perception_pepper/person_features_detection_service2 "{entries_list: {obj: [data : "Human\ face" ,data : "Human\ body" ,data : "Human\ head" ,data : "Human\ arm" ,data : "Human\ hand" ,data : "Human\ nose" ,data : "Person" , data : "Man" , data : "Boy" , data : "Girl" , data : "Woman"] ,  distanceMaximum: 5.0}}" |
| Human features |rosservice call /robobreizh/perception_pepper/person_features_detection_service "{entries_list: [data : "Human\ face" ,data : "Human\ body" ,data : "Human\ head" ,data : "Human\ arm" ,data : "Human\ hand" ,data : "Human\ nose" ,data : "Person" , data : "Man" , data : "Boy" , data : "Girl" , data : "Woman"] }"|
|  | rosservice call /robobreizh/perception_pepper/seat_detection_service "{entries_list:[data: 'SEAT_INFORMATION']}" |


## Navigation