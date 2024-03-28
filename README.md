# Market-CIpher A

//@version=3
study(title="Market Cipher A", overlay=true)
//EMA Ribbon
ema1 = input(5)
ema2 = input(11)
ema3 = input(15)
ema4 = input(18)
ema5 = input(21)
ema6 = input(24)
ema7 = input(28)
ema8 = input(34)
ema1_ = ema(close, ema1)
ema2_ = ema(close, ema2)
ema3_ = ema(close, ema3)
ema4_ = ema(close, ema4)
ema5_ = ema(close, ema5)
ema6_ = ema(close, ema6)
ema7_ = ema(close, ema7)
ema8_ = ema(close, ema8)
plot(ema1_, color=#265aa6, linewidth=2, transp=50, title="EMA 1")
plot(ema2_, color=#265aa6, linewidth=2, transp=50, title="EMA 2")
plot(ema3_, color=#1976d2, linewidth=2, transp=50, title="EMA 3")
plot(ema4_, color=#1976d2, linewidth=2, transp=50, title="EMA 4")
plot(ema5_, color=#7fb3ff, linewidth=2, transp=50, title="EMA 5")
plot(ema6_, color=#7fb3ff, linewidth=2, transp=50, title="EMA 6")
plot(ema7_, color=#bbdefb, linewidth=2, transp=50, title="EMA 7")
plot(ema8_, color=#bbdefb, linewidth=2, transp=50, title="EMA 8")

Longema = crossover(ema2_,ema8_)
plotshape(Longema, style=shape.circle, color=green, transp=0, location=location.abovebar, size=size.tiny, title="Long EMA Signal")
Redcross = crossunder(ema1_,ema2_)
plotshape(Redcross, style=shape.xcross, color=red, transp=0, location=location.abovebar, size=size.tiny, title="Red cross")
Bluetriangle = crossover(ema2_,ema3_)
plotshape(Bluetriangle, style=shape.triangleup, color=blue, transp=0, location=location.belowbar, size=size.small, title="Blue Triangle")

//Alerts
alertcondition(Redcross != 0, "RedX", " RedX")
alertcondition(Longema != 0, "Longema", "Longema")
alertcondition(Bluetriangle!= 0, "Bluetriangle", " Bluetriangle")

//-------------------END-------------------
