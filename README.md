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
fullpower三种模式的特性：从学习资料38.213_Ch7_Steven_202209.pptx中得到：  
1. fullpower下，仅有一个天线端口，单端口满功率。  
2. fullpowerMode1，两路Tx需要共同发射信号以达到总体最大power。  
3. fullpowerMode2，两路Tx一起发送都不一定能够达到总体最大功率，有的路打满，有的路打不满。  

MSG3_DeltaPreamble在331中给出，定义时指出，Actual Value = filed value * 2 (dB) 。  

P_O_UE_PUSCH,b,f,c(1)有两个value，由SRS resource set indicator决定。  
RAN1#107-e会议中Tdoc R1-2112583中说明：  
1. 为了URLLC mTRP改动了SRS resource sets可为两个。  
2. 为了支持指示两个TPMI，SRS端口数应与两个TRP一致。  
RAN1#103-e会议中Tdoc R1-2009480中提案：  
1. SRS resource sets设为2，为每个SRS resource set 配CSI-RS resource。  
2. FFS: SRI field in DCI 改动以强化两种beam的repetition。  

# UL GRANT  
有动态上行调度和无动态授权的传输两种。（Dynamic scheduling & Configured Grant）  
无动态授权的PUSCH传输，即configured grant，有两种TYPE分别为TYPE 1和TYPE 2:  
1. TYPE1为RRC发起的PUSCH传输（个人猜测为UE主动发送用户数据）  
2. TYPE2为PDCCH激活的传输（个人猜测为DCI激活半静态调度的发送，semi-persistent transmission）。
  
Dynamic Grant猜测为NW请求UE发送特定数据。  

# PUSCH repetition(是否是M-TRP PUSCH repetition有待考察)
行为是：在多个slot重复地发送同一个TB。不同于HARQ由NW发送NACK触发重传，这个是UE经过配置后，主动发送。  
由DCI format 0_1或0_2调度。
