### Chavez Americano Cesar    |   No. Control: 17210541


[![Sensor-Infra-Red.png](https://i.postimg.cc/CLvsHbZJ/Sensor-Infra-Red.png)](https://postimg.cc/0bwS9M0J)

Un detector infrarrojo es un tipo de dispositivo que tiene la capacidad de medir la radiación electromagnética infrarroja que emiten los cuerpos que se encuentran dentro de su campo de visión. Se trata de un tipo de radiación que emiten todos los cuerpos de forma independiente a que exista otro tipo de luz ambiental. De este modo, permite observar espacios y objetos sin necesidad de que exista luz visible o de otro tipo en el entorno.

| Sensor | Practica | Código | Prueba |
| --- | --- | --- | --- |
| KY - 022 IR Receiver | Infrarrojo del control remoto | Phyton | https://www.loom.com/share/c468d38a9b9e46b38c77648d3af020b6 |

![Diagrama-del-Sensor-Infrarrojo.png](https://i.postimg.cc/cL45ds3k/Diagrama-del-Sensor-Infrarrojo.png)

```python
#include <IRremote.h>
#define pinSensorIR 11

IRrecv sensorIR(pinSensorIR) ;
decode_results codigoIR;

void setup() {
	Serial.begin(9600);
	sensorIR.enableIRIn();
}

void loop () {
	if (sensorIR.decode(&codigoIR)) {
		Serial.println(codigoIR.value,HEX);
		sensorIR.resume () ;
	}
	delay (100);
}
```


