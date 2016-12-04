# Generalised Impulse Response Function (GIRF) for R package tsDyn

This code allows to use Generalised Impulse Response Function (GIRF) for tsDyn. Code written by Alexander Haider. 

Use:
    
    source("https://raw.githubusercontent.com/MatthieuStigler/tsDyn_GIRF/master/GIRF2")
    library(tsDyn)
    data(zeroyld)

    resT <- TVAR(zeroyld, lag=2, nthresh=2, thDelay=1, trim=0.1, mTh=1, plot=F)

    resGIRF <- GIRF(resT)
    plot(cumsum(resGIRF[,2,3]), type='l')
    plot(resGIRF[,2,3], type='l')
    
There are five arguments:

   - res: estimation result from TVAR
   - hor=20: impulse response horizon
   - shk: shock size (in standard deviations)
   - shVar: shocked Variable
   - replic=100: no. bootstrap replications
    
For more details, see original post on tsDyn mailing list: https://groups.google.com/forum/#!topic/tsdyn/XFF6lKOjqww
