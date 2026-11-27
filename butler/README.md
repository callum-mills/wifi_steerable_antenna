## Schéma sous ADS
Nous commençons par modéliser/optimiser 1 branch-line puis nous pouvons passer au schéma complet (avec design de la matrice butler).     
Nous avons 2 propositions de substrat :      
- le Roger (tan(d)=0.0037 , Er=3.48, h=0.76mm) avec h l'éaisseur du substrat
- le JLCPCB (tan(d)=0.0018 , Er=2.55, h=1.52mm)
Avant de passer au linecalc nous avons fait les calculs à la main avec les formules suivantes :
$$A = \frac{Z_c}{60}\sqrt{\frac{\varepsilon_r + 1}{2}} + \frac{\varepsilon_r - 1}{\varepsilon_r + 1}\left(0,23 + \frac{0,11}{\varepsilon_r}\right)$$
$$B = \frac{377\pi}{2\,Z_c\sqrt{\varepsilon_r}}$$

###Pour $W/h < 2$ :     
$$\frac{W}{h} = \frac{8e^A}{e^{2A} - 2}$$

###Pour $W/h > 2$ :     
$$\frac{W}{h} = \frac{2}{\pi}\left[B - 1 - \ln(2B - 1) + \frac{\varepsilon_r - 1}{2\varepsilon_r}\left(\ln(B - 1) + 0,39 - \frac{0,61}{\varepsilon_r}\right)\right]$$
$$\varepsilon_{\text{eff}} = \frac{\varepsilon_r + 1}{2} + \frac{\varepsilon_r - 1}{2}\left(1 + \frac{12h}{W}\right)^{-1/2}$$

Pour finir : 
$$d = \frac{c}{4\,f\sqrt{\varepsilon_{\text{eff}}}}$$
