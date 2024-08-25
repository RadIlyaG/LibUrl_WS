# RLWS

RLWS used for operate Y.Zinner's WebServices.

It's commands return 2 values: result pass/fail value and result text, includes the rquested data or text describes a problem:  
- **result value**: 0 or -1
- **result text**: value/values of required data; or info about a fail
  
_For example:_  
`::RLWS::Get_SwVersions DC1002287083` returns 0 {SW3814 B1.0.3 SW3841 5.2.0.75.28}  
`::RLWS::Get_SwVersions DE1005790454` returns -1 {No SW Versions for DE1005790454. UUT problem}

In case the RL can't get info from Servers, it performs Connectivity Tests (Ping) to RAD Servers - **webservices03** and **ws-mac-pages** - by `::RLWS::Ping_Services`

#### Meantime the mostly updated and verified file is located at \\prod-svm1\tds\Install\ATEinstall\JATE_Team\LibUrl_WS

## SYNOPSIS
* \::RLWS::CheckMac _id mac_
* \::RLWS::Disconnect_Barcode _id ?mac?_
* \::RLWS::Get_ConfigurationFile _dbr_assm localUserConfFile_
* \::RLWS::Get_CSL _id_
* \::RLWS::Get_MrktName _id_
* \::RLWS::Get_MrktNumber _dbr_assm_
* \::RLWS::Get_OI4Barcode _id_
* \::RLWS::Get_Pages _id ?traceId? ?macs_qty?_
* \::RLWS::Get_PcbTraceIdData _id var_list_
* \::RLWS::Get_SwVersions _id_
* \::RLWS::Get_TraceId _id_
* \::RLWS::MacServer _macs_qty_
* \::RLWS::UpdateDB2 _barcode uut hostDescription date tim status failTestsList failReason operator traceID poNumber ?data1? ?data2? ?data3?_

 color is `#0969DA` fff
## EXAMPLES
One of the ways to operate the RL's command and receive it's result is:  
`foreach {ret ResTxt} [::RLWS::[command]] {}`  
`if {$ret!=0} {`  
  `...`  
`}`
