## Binary Defense Systems   
  https://www.binarydefense.com/banlist.txt

### Overview
Each time the IP list is changed, modified, or updated we keep track of its size (both number of entries and number of unique IPs matched).
Using this information we can detect what the list maintainers do, get an idea of the list trend and its maintainers habbits.

Note that this is for public use only.
  The ATIF feed may not be used for commercial resale or in products that are charging fees for such services.
  Use of these feeds for commerical (having others pay for a service) use is strictly prohibited.

#### Binary Defense IP feed
This feed contains Binary Defense Systems Artillery Threat Intelligence feed and banlist feed

### PRE-REQUISITES to use Binary Defense IP feed API and DNIF  
Outbound access required to request Binary Defense IP feed API 

| Protocol   | Source IP  | Source Port  | Direction	 | Destination Domain | Destination Port  |  
|:------------- |:-------------|:-------------|:-------------|:-------------|:-------------|  
| TCP | AD,A10 | Any | Egress	| github.com | 443 |
| TCP | AD,A10 | Any | Egress	| binarydefense.com | 443 | 



### Using the Binary Defense feed API
 The Binary Defense feed API is found on github at

https://github.com/dnif/enrich-binarydefense

#### Getting started with binarydefense feed API

1. #####    Login to your AD, A10 containers  
   ACCESS DNIF CONTAINER VIA SSH : [Click To Know How](https://dnif.it/docs/guides/tutorials/access-dnif-container-via-ssh.html)
2. #####    Move to the ‘/dnif/<Deployment-key/enrichment_plugin’ folder path.
```
$cd /dnif/CnxxxxxxxxxxxxV8/enrichment_plugin/
```
3. #####   Clone using the following command  
```  
git clone https://github.com/dnif/enrich-binarydefense.git binarydefense
```
### API feed output structure
  | Fields        | Description  |
| ------------- |:-------------:|
| EvtType      | An IP |
| EvtName      | The IOC      |
| IntelRef | Feed Name      |
| IntelRefURL | Feed URL      |
| ThreatType | DNIF Feed Identification Name |      

An example of API feed output
```
{'EvtType': 'IPv4', 
'EvtName': '116.231.65.64',
'AddFields': {
'IntelRef': ['BINARYDEFENSE'],
'IntelRefURL': ['https://www.binarydefense.com/banlist.txt'],
'ThreatType': ['blacklist'] }}
```
