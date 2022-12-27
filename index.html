

#include <DHT.h>
#include <ESP8266WebServer.h>
#include <ESP8266WiFi.h>
#include <Servo.h>
#include "MainPage.h"
Servo myservo;

//tạo port 80
ESP8266WebServer sv(80);

<!-- khai báo biến của các linh kiện điện tử -->
int pos=0;
int servoPin = D4;
float nhietdo;
float doam;
int den1, den2, den3, den4;
int count = 1;
String chuoiSendWebJson = "";
long last = 0;

//Khai báo biến cảm biến nhiệt độ
#define DHTPIN D7      // Chân DATA nối với chân D8
#define DHTTYPE DHT11 // DHT 11Khai báo loại cảm biến, có 2 loại là DHT11 và DHT22
DHT dht(DHTPIN, DHTTYPE); //Khởi tạo cảm biến

char* ssid = "KHANH"; //tên mạng wifi muốn truy cập
char* pass = "0769644600"; //mật khẩu

//IPAddress local_IP(192,168,1,1);
//IPAddress gateway(192,168,1,1);
//IPAddress subnet(255,255,255,0);


<!-- Khai báo các hàm của chương trình -->
void dataJson(String den1, String den2, String nhietdo);
void chuongTrinhCamBien();
void onclick_Button();
void xuLyOnOff(String button);


void setup() {

    
    pinMode(D1, OUTPUT);  //led chân D1
    pinMode(D2, OUTPUT);  //led chân D1
    pinMode(D6, OUTPUT);  //led chân D6

    myservo.attach(servoPin); //khởi tạo servo
    dht.begin(); //khởi tạo cảm biến nhiệt độ
  
  //sử dụng 2 chế độ Access Point Mode & chế độ Station Mode
  WiFi.mode(WIFI_AP_STA);

  // chế độ Access Point Mode
  Serial.println("Setting AP mode");
  WiFi.softAP("ALLK - SMART HOME", "1234567"); 
  IPAddress IP = WiFi.softAPIP();
  Serial.println("Access Point IP address: ");
  Serial.println(IP);

  //chế độ Station Mode
  WiFi.begin(ssid, pass); //kết nối vào mạng wifi

  Serial.begin(115200); //xem ở cổng 115200 ở serial
  Serial.println("connecting");
  while (WiFi.waitForConnectResult() != WL_CONNECTED)
  {
    delay(100);
    Serial.print(".");
  }
  Serial.println("");
  Serial.println("WiFi connected");  //in ra chữ nếu kết nối thành công
  Serial.println("Station Mode IP address: ");
  Serial.println(WiFi.localIP());
  
  sv.on("/", [](){
    Serial.println(String("co nguoi truy cap: ")+ count++); //hiển thị số lượng người truy cập trên serial
    sv.send(200, "text/html", MainPage); //gửi giao diện đến trình duyệt(google, cốc cốc, điện thoại..)
  });

  sv.on("/update", [](){
    dataJson(String(den1), String(den2), String(den3), String(den4), String(nhietdo));
     sv.send(200, "text/html", String(chuoiSendWebJson)); //gửi dữ liệu cảm biến đến client (google, cốc cốc, điện thoại..)
  });

   sv.on("/Button", [](){
      onclick_Button(); //khi click nút trên giao diện
  });


  sv.begin();
  last = millis();


}

void loop() {
   sv.handleClient();
//   if(millis() - last >= 1000){
//      chuongTrinhCamBien();
//      last = millis();
//   }

  // in nhiệt độ độ ẩm ra Serial
  float h = dht.readHumidity();    
  float t = dht.readTemperature();
  Serial.print("Nhiet do: ");
  Serial.println(t);               
  Serial.print("Do am: ");
  Serial.println(h);
 
}


void dataJson(String den1, String den2, String den3, String den4, String nhietdo) {
  chuoiSendWebJson = "{\"den1\":\"" + String (den1) + "\", " +
                      "\"den2\":\"" + String (den2)+ "\", " +
                      "\"den3\":\"" + String (den3)+ "\", " +
                      "\"den4\":\"" + String (den4)+ "\", " +
                      "\"nhietdo\":\"" + String (nhietdo) + "\"}" ;
}

void chuongTrinhCamBien(){
  nhietdo += 1.1;
  if(nhietdo >= 40){
    nhietdo = 0;
  }
}

void xuLyOnOff(String button) {
  if(button == "TB1OFF"){
    Serial.println("Tat Thiet Bi 1");
    digitalWrite(D1, LOW); //tắt D1
    den1 = 0;
  }
  else if(button == "TB1ON"){
    Serial.println("BAT Thiet Bi 1");
    digitalWrite(D1, HIGH);
    den1 = 1;
  }
  else if(button == "TB2OFF"){
    Serial.println("Tat Thiet Bi 2");
    digitalWrite(D2, LOW);
    den2 = 0;
  }
  else if(button == "TB2ON"){
    Serial.println("BAT Thiet Bi 2");
    digitalWrite(D2, HIGH);
    den2 = 1;
  }
   else if(button == "TB3OFF"){
    Serial.println("Tat Thiet Bi 3");
    digitalWrite(D6, LOW);
    den3 = 0;
  }
  else if(button == "TB3ON"){
    Serial.println("BAT Thiet Bi 3");
    digitalWrite(D6, HIGH);
    den3 = 1;
  }
  else if(button == "TB4OFF"){
    Serial.println("Tat Thiet Bi 4");
    myservo.write(0);
    den4 = 0;
  }
  else if(button == "TB4ON"){
    Serial.println("BAT Thiet Bi 4");
    myservo.write(90);
    den4 = 1;
  }
}

void onclick_Button(){
  Serial.println(">>Onclick Button");
  Serial.println(sv.arg("Button"));
  String button = "";
  button = sv.arg("Button");
  xuLyOnOff(String(button));
  sv.send(200, "text/html", MainPage);
  
}