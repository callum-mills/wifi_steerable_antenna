## Schéma sous ADS
Nous commençons par modéliser/optimiser 1 branch-line puis nous pouvons passer au schéma complet (avec design de la matrice butler).    
Nous travaillons à f=2,44GHz ainsi que Z0=50 ohm.     
Nous avons 2 propositions de substrat :      
- le Roger (tan(d)=0.0037 , Er=3.48, h=0.76mm) avec h l'épaisseur du substrat
- le JLCPCB (tan(d)=0.0018 , Er=2.55, h=1.52mm)
        
Avant de passer au linecalc nous avons fait les calculs à la main avec les formules suivantes :     
$$A = \frac{Z_c}{60}\sqrt{\frac{\varepsilon_r + 1}{2}} + \frac{\varepsilon_r - 1}{\varepsilon_r + 1}\left(0,23 + \frac{0,11}{\varepsilon_r}\right)$$     
$$B = \frac{377\pi}{2\,Z_c\sqrt{\varepsilon_r}}$$

Pour $W/h < 2$ :     
$$\frac{W}{h} = \frac{8e^A}{e^{2A} - 2}$$

Pour $W/h > 2$ :     
$$\frac{W}{h} = \frac{2}{\pi}\left[B - 1 - \ln(2B - 1) + \frac{\varepsilon_r - 1}{2\varepsilon_r}\left(\ln(B - 1) + 0,39 - \frac{0,61}{\varepsilon_r}\right)\right]$$     

Pour finir :      
$$\varepsilon_{\text{eff}} = \frac{\varepsilon_r + 1}{2} + \frac{\varepsilon_r - 1}{2}\left(1 + \frac{12h}{W}\right)^{-1/2}$$     et    $$d = \frac{c}{4\,f\sqrt{\varepsilon_{\text{eff}}}}$$

Nous trouvons les résultats suivants :      
- Roger :     
   pour $$Z_c=Z_0=50ohm$$, $$W_{r1}=1,724mm$$ et $$d_{r1}=18,588mm$$     
  pour $$Z_c=Z_0/\sqrt{2}=35,35ohm$$, $$W_{r2}=2,886mm$$ et $$d_{r2}=18,214mm$$
- JLCPCB :     
   pour $$Z_c=Z_0=50ohm$$, $$W_{j1}=4,25826mm$$ et $$d_{j1}=21,15mm$$     
  pour $$Z_c=Z_0/\sqrt{2}=35,35ohm$$, $$W_{j2}=6,99189mm$$ et $$d_{j2}=20,804mm$$

  On prend donc le substrat le plus épais avec la permittivité la plus faible
