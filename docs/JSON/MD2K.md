# MD2K software

## MD2K Data Collection

### Time Series Data Format
TODO: Needs a description of fields here

```json
{
  "uuid": 123456789,	
 "study_id": 123456789,
 "person_id": 23456789,
  "phone_id": 3456789,
  "data": [
    {
      "sensor_type": "AutoSense_Chest (other options: AutoSense_Wrist, Phone, Zaphyr)",
      "sensor_id": "22",
      "channel_id": "33",
      "values": [
        {
          "timestamp": "2015-01-29T08:17:14.625911Z",
          "delta_time_seconds": 0.0,  // delta time as a float
          "values": [
            "3.38",
            "3.88"
          ]
        },
        {
          "timestamp": "2015-01-29T08:17:14.629586Z",
          "delta_time": 0.0,
          "values": [
            "8.88",
            "9.89"
          ]
        }
      ]
    },
    {
      "sensor_type": "AutoSense_Wrist",
      "sensor_id": "88",
      "channel_id": "99",
      "values": [
        {
          "timestamp": "2015-01-29T08:17:14.631122Z",
          "delta_time": 0.0,
          "values": [
            "9.18",
            "8.188"
          ]
        }
      ]
    }
  ]
}
```

### Proposed Cassandra table layout:

```
CREATE TABLE datastreams (

uuid text,
study_id text,
participant_id text,
phone_id text,

sensor_type text,
sensor_id text,
channel_id text,

date text,
timestamp timestamp,

metadata map<text,text>,

delta decimal,
values list<decimal>,
blob_value blob,

);
```
