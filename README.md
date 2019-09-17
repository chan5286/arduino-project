<arduino code>

void setup() {
  Serial.begin(9600);
}
int a;
void loop() {
  int a = analogRead(A0);
  Serial.println(a);
  if(a>255) a=0;
  delay(500);
}


<processing code>

import processing.serial.*;

Serial p;

void setup(){
  size(300,300);
  p=new Serial(this, "COM4", 9600);
}
void draw(){
  if(p.available()>0){
    String m=p.readString();
    int a = int(m.trim());
    println(a);
    if(a>900) fill(255,255,0);
    else if(a<900&&a>450) fill(255,0,0);
    else if(a<450&&a>100) fill(0,255,0);
    else fill(0,0,255);
    ellipse(150, 150, 200, 200);
  }
}

Cds로 측정된 수가 900 초과일 경우 노랑,
                 900 미만 450 초과일 경우 빨강,
                 450 미만 100 초과일 경우 초록,
                 100 미만일 경우 파랑색의 원을 출력 합니다.
              

소감. 이제 막 배우기 시작한 아두이노와 함께 수업에서 처음으로 자바를 써보는 것이 매우 설레었습니다. 아두이노를 자유자재로 다룰 수 있게 수업뿐만 
      아니라 스스로 공부하도록 노력하겠습니다.
