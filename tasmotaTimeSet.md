# Tasmota timezone configuration

> Timezone set offset from UTC 
set Timezone to 99 to configure DST - STD 

> TimeSTD
> TimeDST

```
0 = reset parameters to firmware defaults
H,W,M,D,h,T
H = hemisphere (0 = northern hemisphere / 1 = southern hemisphere)
W = week (0 = last week of month, 1..4 = first .. fourth)
M = month (1..12)
D = day of week (1..7 1 = sunday 7 = saturday)
h = hour (0..23)
T = timezone (-780..780) (offset from UTC in MINUTES - 780min/60min=13hrs)
```

Italy settings

```
Timezone 99
TimeDST 0,0,3,1,2,120
TimeSTD 0,0,10,1,3,60
```



