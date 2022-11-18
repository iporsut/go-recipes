# ใช้ make สร้าง slice

เราใช้ฟังก์ชัน make สร้าง slice ได้โดยส่วนใหญ่ที่ใช้จะมีอยู่ 2 patterns คือกำหนด length ไปเลย กับ กำหนด length เป็น 0 แล้วกำหนด capacity แทน

แบบแรก กำหนด length คือเราต้องการสร้าง slice มี slot ตามที่เราต้องการเลย แต่ว่าค่าในแต่ละ elements เป็น zero value (defaul value ของ type ที่เราเลือกให้กับ element ของ slice)

```go
numbers := make([]int, 10)
```

แบบนี้ numbers ก็คือ slice ของ int ที่มีจำนวน 10 ตัวโดยแต่ละตัวค่าเริ่มต้นเป็น 0

```go
fmt.Println(numbers) // output: [0 0 0 0 0 0 0 0 0 0]
```

อีกแบบคือเราสร้าง length เป็น 0 ก่อนแต่ใช้ make เพื่อเตรียมพื้นที่ล่วงหน้าโดยกำหนด capacity แทน ทำให้เวลาเรา append ของเพิ่มใน slice ไม่ต้องไปจอง memory เพิ่มบ่อยๆ ลดเวลาลงไปได้ โดยใช้ make แบบนี้

```go
numbers := make([]int, 0, 10)
```

แบบนี้ถ้าเราไปปริ้น เราจะเห็นมันเป็น slice ว่างๆ
```go
fmt.Println(numbers) // output: []
```

เราเอาไป append ได้ปกติ
```go
numbers = append(numbers, 0, 1, 2, 3)
fmt.Println(numbers) // output: [0 1 2 3]
```


แต่ถ้าเราไม่แคร์ capacity เริ่มต้น เราอยากได้ slice ว่างๆแบบพร้อมเอาไป append เราก็ประกาศไว้แค่ตัวแปรแบบนี้ก็ได้

```go
var numbers []int
numbers = append(numbers, 0, 1, 2, 3)
fmt.Println(numbers) // output: [0 1 2 3]
```

หรือถ้าเราไม่อยากให้มันเป็น nil แต่เป็น empty slice ก็ใช้ slice literal แทน make ก็ได้
```go
numbers := []int{}
numbers = append(numbers, 0, 1, 2, 3)
fmt.Println(numbers) // output: [0 1 2 3]
```
