# WSAdapter

My Ecowitt to Telegraf Weather Station Adapter.

Provides a Webservice that takes Weatherdata in the Ecowitt format to be read by Telegraf.
Tested with WH3000SE.

#### Telegraf Config:
    [[inputs.http]]
     name_override = "weather"
     urls = [
         "http://x.x.x.x:8080/get_data"
     ]
     interval = "60s"
     data_format = "json"

    [[outputs.influxdb]]
     urls = ["http://x.x.x.x:8086"]
     database = "weather"
     timeout = "0s"
     retention_policy = ""
