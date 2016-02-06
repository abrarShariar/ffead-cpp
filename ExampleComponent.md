# Example Component Configuration #
```
#The Component Name, Should be unique
@CMP_NAME=TEST_BEAN

#The Component Description
@CMP_DESC=Test Bean

#Is The Component available Through Ajax
@AJAX_AVAIL=true

#Is the Component exposed as a Web-Service
@WEBS_AVAIL=true

#Can the Component be additionally invoked using MI
@MINV_AVAIL=true

#Is AUTO Trnsaction enabled?
@AUTO_TRANS=true

#The Threading Strategy
@THRD_PER_REQ=false

#The Thread Pool size
@THRD_POOL_NUM=20

#The Authorization source
@AUTH_FROM=database

#The Details of the Auth Source
@AUTH_DETS=@DB

#Is Authorization required for All Services?
@AUTH_ALL=false

#The User Groups that can access the Services
@USR_GRP_ALWD=UG_1,UG_2,UG_3

#The Users that are Blocked.
@BLOCK_USERS=user1,user2

#The Protocols allowed
@PROTO_ALWD=tcp,http,udp

#The DB connection Pool Size
@DB_CONN_POOL_NUM=10

#The Auth Connection Source
@AUTH_CONN_SRC=test_dsn

#The Auth Source User Name
@AUTH_USR_NAME=test

#The Auth Source User Password
@AUTH_USR_PASS=test

#The Auth Source Address
@AUTH_ADD=

#Are Sessions allowed
@SESSION=false

#The Service Details
#@NAME is the Service Name
#@USR_GRP_ALWD are the User Groups allowed to access the Component
#@SIGNATURE is the Service signature
#@ARGS are the arguments required for the Service
#SRV_RET is the Service Return type
@SERVICE1=@NAME(myFirstService) @USR_GRP_ALWD(UG_1,UG_2) @SIGNATURE(Service1.service1) @ARGS(void) @SRV_RET(string)
@SERVICE2=@NAME(mySecondService) @BLOCK_USERS(user7) @SIGNATURE(Service2.service2) @ARGS(string) @SRV_RET(string)
```