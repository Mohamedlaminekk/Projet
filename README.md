# Projet
#include <IRremote.h>
#include <Servo.h>
#include <Wire.h>
#include <Adafruit_PWMServoDriver.h>

Adafruit_PWMServoDriver myServo = Adafruit_PWMServoDriver();

#define SERVOMIN 150
#define SERVOMAX 380
#define SERVOMIN_1 150
#define SERVOMAX_1 380
int PIN_IR = 8;
int iValue;
uint8_t servonum = 0;
uint8_t numberOfServos = 6;

void setup()
{
 myServo.begin();
 myServo.setPWMFreq(60);
 delay(10);
 Serial.begin(9600);
 IrReceiver.begin(PIN_IR); //Déclaration/Initialisation de mon objet IR
 pinMode(7,OUTPUT);
}

void loop() {
     if ( IrReceiver.decode() ) {
       iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
       Serial.println(iValue);
       IrReceiver.resume(); //Important
       }

/* do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
 }
 delay(100);
 }while(iValue == iValue); */
int valeur = iValue;
 switch (iValue) {
 case 12:
   {
delay(3000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1

delay(1000);
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
 }
 delay(100);
 }while(valeur == iValue);
 delay(1000);
}
   break;
   case 24:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(5, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
      case 94:
   {
delay(3000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
         case 8:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
  // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
            case 28:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
// Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
               case 90:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(5, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
                  case 66:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
// Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
    case 82:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
  // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(5, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
                        case 74:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
 // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(3, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
                        case 22:
   {
delay(1000);
// remettre à zero
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(0, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(1, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(2, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(3, 0, pulselen);
}

for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(4, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(5, 0, pulselen);
}
for (uint16_t pulselen = SERVOMAX; pulselen > SERVOMIN; pulselen--){
 myServo.setPWM(6, 0, pulselen);
}
// Affiche le chiffre 1
  // Segment 2
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(0, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(2, 0, pulselen);
}

 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(4, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN; pulselen < SERVOMAX; pulselen++){
 myServo.setPWM(5, 0, pulselen);
}
 // Segment 5
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(6, 0, pulselen);
}
 for (uint16_t pulselen = SERVOMIN_1; pulselen < SERVOMAX_1; pulselen++){
 myServo.setPWM(1, 0, pulselen);
}
 delay(100);
do {
   if ( IrReceiver.decode() ) {
   iValue = IrReceiver.decodedIRData.command; // Valeur en décimal
   Serial.println(iValue);
   IrReceiver.resume(); //Important
   delay(100);
 }
 }while(valeur == iValue);
 delay(1000);
}
   break;
   default:
   Serial.println(iValue);
   break;
  }
   }
