# ใช้ make สร้าง map

map ถ้าเราประกาศตัวแปรเฉยๆ ค่ามันจะเป็น nil ซึ่งเราจะเอาไปเพิ่ม key, value ใหม่ไม่ได้เลย มันจะ panic

```go
var m map[string]string
m["name"] = "Somsak" // panic !!!!
```

make เป็นอีกวิธีในการ initialize empty map คือทำให้มันไม่ nil พร้อมใช้งานในการเพิ่ม key, value โดยที่หลังจาก make แล้ว elements ใน map ยังว่างๆเป็น 0 อยู่

วิธีใช้แค่เรียก make พร้อมใส่ type map ที่เราต้องการ

```go
var m = make(map[string]string) // หรือ m := make(map[string]string)
m["name"] = "Somsak"
```

แต่บางทีเราก็ไม่ใช่ make กับ map ก็ได้เพราะมันเขียนแบบนี้ได้ โดยใช้ literal map
```go
m := map[string]string{}
m["name"] = "Somsak"
```
