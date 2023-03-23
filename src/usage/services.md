# Services

- [Services](#services)
  - [Perception](#perception)
  - [Dialog](#dialog)
  - [Navigation](#navigation)

## Perception

| Function    | Service |
| ----------- | ----------- |
| All objects | /robobreizh/perception_pepper/object_detection_service "{entries_list:[data: 'ALL']}"|
| Person and chair | /robobreizh/perception_pepper/object_detection_service "{entries_list: [data : "person", data : "chair"] }" |
| Human features with distance |  /robobreizh/perception_pepper/person_features_detection_distance_service "{entries_list: {obj: [data : "Human\ face" ,data : "Human\ body" ,data : "Human\ head" ,data : "Human\ arm" ,data : "Human\ hand" ,data : "Human\ nose" ,data : "Person" , data : "Man" , data : "Boy" , data : "Girl" , data : "Woman"] ,  distanceMaximum: 5.0}}" |
| Human features |/robobreizh/perception_pepper/person_features_detection_service "{entries_list: [data : "Human\ face" ,data : "Human\ body" ,data : "Human\ head" ,data : "Human\ arm" ,data : "Human\ hand" ,data : "Human\ nose" ,data : "Person" , data : "Man" , data : "Boy" , data : "Girl" , data : "Woman"] }"|
| Seat | /robobreizh/perception_pepper/seat_detection_service "{entries_list:[data: 'SEAT_INFORMATION']}" |
| Wave hand | /robobreizh/perception_pepper/wave_hand_detection "distance_max: 5.0"|
| posture detection |/robobreizh/perception_pepper/person_features_detection_posture "{entries_list:{ obj:[data: ''],  distanceMaximum: 5.0}}"|
| shoes and drink | /robobreizh/perception_pepper/shoes_and_drink_detection_service "{entries_list: [data: 'SHOES_DRINK_INFORMATION']}"|
| pointing at | /robobreizh/perception_pepper/pointing_hand_detection  "distance_max: 5.0"|

## Dialog

| Function    | Service |
| ----------- | ----------- |
| Find if the name is known | /robobreizh/dialog_pepper/transcript_contains_srv "{transcript:'My name is Angel',word_found:'Name'}"|
| Find the intent of the transcript | /robobreizh/dialog_pepper/transcript_intent "{transcript:''}"|

## Navigation
