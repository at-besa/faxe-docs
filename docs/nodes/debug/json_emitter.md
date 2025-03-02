The json_emitter node
=====================

This node is for debugging and testing/mocking purposes.

It periodically and randomly emits one of the json strings given with the `json` parameter.

Example
-------
```dfs  
|json_emitter()
.every(3s)
.json(' {"condition": {"id": 0, "name": "OK"}, "condition_reason": "", 
        "predicted_maintenance_time": 1584246411783,
    "vac_on_without_contact": [1.2, 2.5, 4.33], "vac_on_with_contact": [5.6, 45.98, 7.012]} ',
  ' {"condition": {"id": 1, "name": "Warning"}, "condition_reason": "bad succer", 
        "predicted_maintenance_time": 1583246411783,
     "vac_on_without_contact": [0.2, 2.5, 8.01], "vac_on_with_contact": [6.001, 4.798, 7.012]} ',
  ' {"condition": {"id": 2, "name": "Error"}, "condition_reason": "something went really wrong!", 
        "predicted_maintenance_time": 1582246411783,
     "vac_on_without_contact": [0.5, 2.5, 0.44], "vac_on_with_contact": [2.06, 4.98, 2.901]} '
     )
 
|debug()
```
     
Emit one of the three given json strings(selected randomly) every 3 seconds.

Parameters
----------

Parameter     | Description | Default 
--------------|-------------|---------  
every( `duration` ) | emit interval| 5s
jitter( `duration` )  | add time jitter to the values produced| 0ms
json( `string_list` ) | list of json strings |
align( is_set )|align the time to the every param|false (not set)
