void lcd_send_nibble(byte nibble) {
  digitalWrite(5, (nibble >> 0) & 1);
  digitalWrite(4, (nibble >> 1) & 1);
  digitalWrite(3, (nibble >> 2) & 1);
  digitalWrite(2, (nibble >> 3) & 1);

  digitalWrite(11, HIGH);
  delayMicroseconds(1);
  digitalWrite(11, LOW);
  delayMicroseconds(100);
}

void lcd_command(byte cmd) {
  digitalWrite(12, LOW);
  lcd_send_nibble(cmd >> 4);
  lcd_send_nibble(cmd & 0x0F);
  delay(2);
}

void lcd_data(byte data) {
  digitalWrite(12, HIGH);
  lcd_send_nibble(data >> 4);
  lcd_send_nibble(data & 0x0F);
  delay(2);
}

void lcd_print(const char *str) {
  while (*str) lcd_data(*str++);
}

void lcd_init() {
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(2, OUTPUT);

  delay(50);

  digitalWrite(12, LOW);
  lcd_send_nibble(0x03); delay(5);
  lcd_send_nibble(0x03); delay(5);
  lcd_send_nibble(0x03); delay(5);
  lcd_send_nibble(0x02);

  lcd_command(0x28);
  lcd_command(0x0C);
  lcd_command(0x01);
  delay(5);
}

void scroll_text(const char *msg) {
  lcd_command(0x01);
  delay(2);
  lcd_print(msg);

  for(int i=0; i<16; i++){
    lcd_command(0x18);
    delay(300);
  }
}

void setup() {
  lcd_init();
}

void loop() {
  scroll_text(" HELLO AYOOSH ");
  delay(1000);
}
