# Fabric-Demo-Employee-App
A demo application built on hyper ledger fabric to add employees and read them
This demo app has been built on top of fabcar demo app from Hyperledger fabric

## Gist
1. [chaincode/emplist](https://github.com/SujithSizon/Fabric-Demo-Employee-App/tree/master/chaincode/emplist) contains the updated the chaincode that will be used in this application.
2. Line 20, 48, 49 and 51 [startFabric.sh](https://github.com/SujithSizon/Fabric-Demo-Employee-App/blob/master/emplist/startFabric.sh) have been edited to include the new chaincode.
3. [query.js](https://github.com/SujithSizon/Fabric-Demo-Employee-App/blob/master/emplist/javascript/query.js) contains api definitions for querying the blockchain.
4. [angularApp/](https://github.com/SujithSizon/Fabric-Demo-Employee-App/tree/master/emplist/javascript/angularApp) contains the code for frontend application which consumes the above api endpoints.

## Setup
1. Copy the folder Fabric-Demo-Employee-App/chaincode/emplist (the chaincode) and place it inside your local_dir/fabric-samples/chaincode/
2. Copy the folder Fabric-Demo-Employee-App/emplist (the application) and place it inside local_dir/fabric-samples/
3. cd local_dir/fabric-samples/first-network
4. sudo ./byfn.sh down
5. sudo docker rm -f $(sudo docker ps -aq)
6. sudo docker rmi -f $(sudo docker images | grep fabcar | awk '{print $3}')
7. sudo docker rmi -f $(sudo docker images | grep emplist | awk '{print $3}')
8. cd local_dir/fabric-samples/emplist
9. sudo ./startFabric.sh javascript
10. cd local_dir/fabric-samples/emplist/javscript
11. npm install
12. cd local_dir/fabric-samples/emplist/javscript/angularApp
13. npm install -g @angular/cli
14. npm install
##### {Spawn Terminal 2 and excute the following command}
15. ng serve -o
##### {Go back to Terminal 1 and excute the following commands}
16. cd local_dir/fabric-samples/emplist/javscript
17. node enrollAdmin.js
18. node registerUser.js
19. node query.js
20. open http://localhost:4200/ in your browser and press button to list of all employees
21. add more employees using invokeJS and view them using query.js


## Endpoints
> GET /api/getAllEmps

<img src="https://raw.githubusercontent.com/SujithSizon/Fabric-Demo-Employee-App/master/080f0425-28db-4828-9bf7-05a7e523e64e.jpg" width="200">

## Future Work
> GET /api/getEmp/{empid}

> POST /api/addEmp


