# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# General to Specific Modelling and Indicator Saturation in 2SLS Models Use gets (ivgets) With (In) R Software
install.packages("ivgets")
library("ivgets")
ivgets = read.csv("https://raw.githubusercontent.com/timbulwidodostp/ivgets/main/ivgets/ivgets.csv",sep = ";")
# Estimation General to Specific Modelling and Indicator Saturation in 2SLS Models Use gets (ivgets) With (In) R Software
fml <- y ~ -1+x1+x2+x3+x4+x5+x6+x7+x8+x9+x10+x11 | -1+x1+x2+x3+x4+x5+x6+x7+x8+x9+x10+z11+z12
base <- ivreg(formula = fml, data = ivgets)
indicators <- isat(base, iis = TRUE, t.pval = 1/100, print.searchinfo = FALSE)
selection <- gets(indicators$final, keep_exog = indicators$selection$ISnames, print.searchinfo = FALSE)
summary(selection$final)
# General to Specific Modelling and Indicator Saturation in 2SLS Models Use gets (ivgets) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished