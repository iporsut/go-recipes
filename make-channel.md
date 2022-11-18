# ใช้ make สร้าง channel

ตัวแปร channel ถ้าเราประกาศตัวแปรเฉยๆจะเป็น nil ซึ่งเอาไปใช้งานพฤติกรรมมันคือ blocking ทั้งตอน send และ receive

ทีนี้ถ้าเราอยากกำหนดค่าเริ่มต้นใน channel มันทำได้วิธีเดียวคือใช้ make เพราะมันไม่มี channel literal syntax

วิธีใช้ก็ง่ายๆ เรียก make แล้วใส่ชื่อ type channel ลงไป

```go
var ch = make(chan int) // หรือ ch := make(chan int)
```

แบบนี้จะได้ unbuffer channel

ถ้าอยากได้ channel แบบมี buffer ก็แค่ใส่จำนวน buffer เป็นค่าที่สองของ make

```go
var ch = make(chan int, 10) // หรือ ch := make(chan int, 10)
```
