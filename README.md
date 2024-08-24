# RLWS

RLWS used for operate Y.Zinner's WebServices.

It's commands return 2 values: result pass/fail value and result text, includes the rquested data or text describes a problem:  
- **result value**: 0 or -1
- **result text**: value/values of required data; or info about a fail
  
_For example:_  
`::RLWS::Get_SwVersions DC1002287083` returns 0 {SW3814 B1.0.3 SW3841 5.2.0.75.28}  
`::RLWS::Get_SwVersions DE1005790454` returns -1 {No SW Versions for DE1005790454. UUT problem"}

In case the RL can't get info from Servers, it performs Connectivity Tests (Ping) to RAD Servers - **webservices03** and **ws-mac-pages** - by `::RLWS::Ping_Services`

#### Meantime the mostly updated and verified file is located at [TDS](\\prod-svm1\tds\install\ate-install\jer_ateTeam\LibUrl_WS)
