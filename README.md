# 5G-NR-RSRP-and-PathLoss-in-dBm-
#Macro to convert reported RSRP level to dBm 

#convert from RSRP value to RSRP dBm
# The reporting range of SS-RSRP for L3 reporting 
#is defined from -156 dBm to -31 dBm with 1 dB resolution. 
# The reporting range of SS-RSRP and CSI-RSRP for L1 reporting 
# is defined from -140 to -40dBm with 1dB resolution.


# RSRP_17 -140≤ SS-RSRP<-139  RSRP<-139 dBm
# RSRP_18 -139≤ SS-RSRP<-138 -139≤ RSRP<-138 dBm

#L1 conversion 
import math as mt 

RSRP_value=float(input("Please enter RSRP value here "));
RSRP_diff= -17+RSRP_value;
RSRP_dBm = RSRP_diff-140;
print("\nRSRP dBm = %.2f"  %RSRP_dBm); 

# The reporting range of SS-RSRQ is defined from -43 dB to 20 dB with 0.5 dB resolution. The mapping of measured
# quantity is defined in Table 10.1.11.1-1. The range in the signalling may be larger than the guaranteed accuracy range.

# SS-RSRQ_0      SS-RSRQ<-43   dB
# SS-RSRQ_1 -43≤ SS-RSRQ<-42.5 dB

RSRQ_value=float(input("Please enter RSRQ value here "));
# RSRQ_diff= -0+RSRQ_value;
RSRQ_dB = RSRQ_value*0.5-43.5;
print("\nRSRQ dB = %.2f"  %RSRQ_dB); 

# # The reporting range of SS-SINR is defined from -23 dB to 40 dB with 0.5 dB resolution. The mapping of measured
# # quantity is defined in Table 10.1.16.1-1. The range in the signalling may be larger than the guaranteed accuracy range. 38.133

RSSINR_value=float(input("Please enter RSSINR value here "));
RSSINR_dB = RSSINR_value*0.5-23.5;
print("\nRSSINR dB = %.2f"  %RSSINR_dB); 

# def Pathloss_Nr(SSRSRP_Nr,SS_Block_Power):
SSRSRP_Nr=float(input("Please enter SSRSRP_Nr value here "));
SS_Block_Power=float(input("Please enter SS_Block_Power value here "));
SS_Block_Power_per_RE = 10*mt.log10((mt.pow(10,SS_Block_Power/10))/240)
print("\nSSS_RS_EPRE dB = %.3f" %SS_Block_Power_per_RE);
PL=SS_Block_Power_per_RE-SSRSRP_Nr
print("\nPL dB = %.3f" %PL);     

