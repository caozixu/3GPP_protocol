# 3GPP 缩略语
nrof = number of  
SI = system information（Other SI会触发RA过程，是RA的一个场景）  
CR = contention resolution（竞争解决）

# 3GPP查看协议为什么这么做  
会议-->Work Agreement-->T-doc。  

# RA
2-step RA fallback到4-step之后，若CR fail，之后依旧会回到2-step RA的MSGA发送。

# 功率控制
为什么需要FullPowerTransmission将上行功率达到最大？  
需要日后确定。  

MSG3_DeltaPreamble在331中给出，定义时指出，Actual Value = filed value * 2 (dB) 。

