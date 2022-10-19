# 3GPP 缩略语
nrof = number of  
SI = system information（Other SI会触发RA过程，是RA的一个场景）  
CR = contention resolution（竞争解决）

# 3GPP查看协议为什么这么做  
会议-->Work Agreement-->T-doc。  

# RA
2-step RA fallback到4-step之后，若CR fail，之后依旧会回到2-step RA的MSGA发送。

# 功率控制
为什么需要FullPowerTransmission将上行功率达到最大？ （需要日后确定）  

MSG3_DeltaPreamble在331中给出，定义时指出，Actual Value = filed value * 2 (dB) 。  

P_O_UE_PUSCH,b,f,c(1)有两个value，由SRS resource set indicator决定。  
RAN1#107-e会议中Tdoc R1-2112583中说明：  
1. 为了URLLC mTRP改动了SRS resource sets可为两个。  
2. 为了支持指示两个TPMI，SRS端口数应与两个TRP一致。  
3. 


# UL GRANT  
有动态上行调度和无动态授权的传输两种。（Dynamic scheduling & Configured Grant）
