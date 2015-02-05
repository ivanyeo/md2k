# MD2K Data Logger POST Format

**Field Specification**

*ouch_token (access_token)* - OAuth2 provided access token

*GCM (registration_Id)* - Registration ID provided by Google Cloud Messaging (GCM)

*study_id (uuid)* - Study ID from the database (128-bit value)

*person_id (uuid)* - unique identifier for each person in the system (128-bit value)

*sensor_type (string)* - Description of the sensor 

*sensor_id (string)* - unique identifier for the sensor

*result (uuid)* - UUID of the appropriate time series data stream

### Time Series Stream Configuration

POST
```json
{
  "oauth_token": access_token,
  "GCM": "APA91bFqnQzp0z5IpXWdth1lagGQZw1PT..........",
  "study_id": 123e4567-e89b-12d3-a456-426655440000,
  "person_id": de305d54-75b4-431b-adb2-eb6b9e546013,
  "sensor_type": "AutoSense_Chest_Accelerometer)",
  "sensor_id": "22"
}
```

RESULT
```json
{
  "tsuuid": uuid
}
```



# Time Series Data Format

**Field Specification**

*oauth_token (access_token)* - OAuth2 provided access token

*timestamp(ISO 8601)* - ISO 8601 with granularity up to microseconds

*data (list)* - samples from a set of sensors; 

*delta_time_seconds (decimal)* - decimal representation of the value of a delta in seconds (Optional)

*value (string)* - Individual data value associated with a single timestamp.  If this is specified, *delta_time_seconds* and *values* will be ignored

*values (list<string>)* - List of string values associated with a single timestamp.  *delta_time_seconds* must be specified

*binary_data (blob)* - Can be used in place of *value* to store binary data


JSON Format
```json
{
  "oauth_token": access_token,
  "data": [
    {
      "tsuuid": 123e4567-e89b-12d3-a456-42665544000,
      "timestamp": "2015-01-29T08:17:14.625911Z",
      "value": '123.45"
    },
    {
      "tsuuid": 123e4567-e89b-12d3-a456-42665544000,
      "timestamp": "2015-01-29T08:17:14.625911Z",
      "binary_data": Base64('foobar.jpg')
    },

    {
      "tsuuid": 123e4567-e89b-12d3-a456-42665544000,
      "timestamp": "2015-01-29T08:17:14.629586Z",
      "delta_time_seconds": 0.001,
      "values": [
        "8.88",
        "9.89"
      ]
    },
    {
      "tsuuid": 123e4567-e89b-12d3-a456-42665544000,
      "timestamp": "2015-01-29T08:17:14.631122Z",
      "delta_time_seconds": 0.0,
      "values": [
        "9.18",
        "8.188"
      ]
    }
   ]
}
```
