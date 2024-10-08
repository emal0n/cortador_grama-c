# Sobre o Projeto
O cortador de grama automativo foi um projeto desenvolvido no Senai, com objetivo de desafiar e treinar todo conhecimento adquirido com a linguagem C e Fundamentos.

## Linguagem Utilizada
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)

## Componetes Utilizados
- Sensor ultrassônico
- Motor corrente continua
- Protoboard
- Arduino
- Suporte
- Baterias (9V)
- Motores DC
- Roda boba
- Helice c/ laminas
- Estrutura geral para aplicação 

## Código - C
```bash
# Portas
int trig = 10;
int echo = 9;
int motorB1A = 2;
int motorB1B = 3;
int motorA1A = 4;
int motorA1B = 5;
int gira = 7;
float distancia; # Declaração de Distancia

void setup() {
  pinMode(motorB1B, OUTPUT);
  pinMode(motorB1A, OUTPUT);
  pinMode(motorA1B, OUTPUT);
  pinMode(motorA1A, OUTPUT);
  pinMode(gira, OUTPUT);
  pinMode(trig, OUTPUT);//saida = transmissor que vai transmitir a onda
  pinMode(echo, INPUT);
  Serial.begin(9600);
}
  
void loop() {
  digitalWrite(trig, LOW);
  delayMicroseconds(5);
  digitalWrite(trig, HIGH);
  delayMicroseconds(10); 
  digitalWrite(trig, LOW);
  
  distancia = pulseIn (echo, HIGH);
  distancia = distancia/58;
  
  Serial.println (distancia);

  if (distancia<100){
  digitalWrite (motorB1B, LOW);
  digitalWrite (motorA1B, LOW);
  digitalWrite (motorA1A, LOW);
  digitalWrite (motorB1A, LOW);
  digitalWrite (gira, LOW);
  Serial.println("Parar");
    
  digitalWrite (motorB1B, LOW);
  digitalWrite (motorA1B, HIGH);
  digitalWrite (motorA1A, LOW);
  digitalWrite (motorB1A, HIGH);
  digitalWrite (gira, LOW);
  Serial.println("Esquerda");
  delay (150);

    digitalWrite (motorB1B, LOW);
  digitalWrite (motorA1B, LOW);
  digitalWrite (motorA1A, LOW);
  digitalWrite (motorB1A, LOW);
  digitalWrite (gira, LOW);
  Serial.println("Parar");
  }  else{
  digitalWrite (motorA1B, HIGH);
  digitalWrite (motorB1B, HIGH);
  digitalWrite (motorA1A, LOW);
  digitalWrite (motorB1A, LOW);
  digitalWrite (gira, HIGH);
  Serial.println("Frente");
  delay (500);  
  } 
}
```
## Imagens do Projeto
![foto](https://raw.githubusercontent.com/emal0n/cortador_grama-c/main/raw/b.jpg)
![foto](https://raw.githubusercontent.com/emal0n/cortador_grama-c/main/raw/c.jpg)
![foto](https://raw.githubusercontent.com/emal0n/cortador_grama-c/main/raw/d.jpg)
## Integrantes da Equipe
```bash
Edmundo N. "(emal0n)"
Gabrielle M. "(gsp2019)"
João P. "(Jotape612)"
Gabriel S. "(?)"
Karol C. "(crqlo)"
```
