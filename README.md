# Node-RED käyttö Raspberry Pi tietokoneella.
 
 Tämä sivusto on tehty tukemaan opinnäytetyöni materiaalia. Tässä esimerkki ohjelmakoodia, jota tein opinnäytetyötäni varten.
 
![alt text](https://github.com/MarcoBrandt/ONT-koodia/blob/main/Screenshot%202021-02-25%20172648.png)

Inject-node, 10 sekunnin repeat.

Raspberry prosessorin lämpötila
```
vcgencmd measure_temp
```

Asteluvun erotus
```
str = msg.payload;
msg.payload = Number(str.substring(5,9));
return msg;
```

Asteluvun aikaleima
```
var today = new Date();
var time = today.toLocaleTimeString();
var date = today.getDate()+'.'+(today.getMonth()+1)+'.'+today.getFullYear();

msg.payload = date + " " + time + ", " + msg.payload + " C";

return msg;
```

Dashboardin elementit ottavat tiedot vastaan ja tulostavat ne Raspberryn Node-RED UI sivustolle.
