###How to use CURL###
```curl -X :httpVerb --data "param1=value&param2=value2" "website url"```

--data "..." is for post parameters

-X :httpVerb specifies which HTTP verb to use (GET, POST, PUT, DELETE)

E.g:

```curl -X GET "http://dev.evitics.com/api/user/cbookman3"```
```curl -X PUT --data "meetingName=Donut Friday" "http://dev.evitics.com/api/meeting/2"```
```curl -X POST --data "meetingName=My Cool Meeting" "http://dev.evitics.com/api/meeting/2/3"```
```curl -X DELETE "http://dev.evitics.com/api/meeting/2/3```
```curl -X GET "http://dev.evitics.com/api/log/2014/December/1/2?page=1"```
