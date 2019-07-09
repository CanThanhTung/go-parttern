# Builder Pattern

Builder pattern trong bộ Creational design patterns. Nó giúp chúng ta xây dựng
các objects phức tạp mà không cần trực tiếp khởi tạo cấu trúc của chúng hoặc
viết logic mà chúng yêu cầu. Hãy tưởng tượng một đối tượng có thể có hàng tá các
fields có cấu trúc phức tạp hơn. Bây giờ hãy tưởng tượng rằng bạn có nhiều đối
objects với những đặc điểm này, và bạn có thể có nhiều hơn nữa. Chúng ta không
muốn viết logic để tạo tất cả các objects trong package, chỉ cần sử dụng các objects.

## implementation

```go
package builder

type Speed float64
type Color string
type Automaker string

const (
	MPH Speed = 1
	KPH       = 1.60934
)

const (
	COLOR_BLUE  Color = "blue"
	COLOR_GREEN       = "green"
	COLOR_RED         = "red"
)

const (
	MAZDA    Automaker = "Mazda"
	MERCEDES           = "Mercedes"
	AUDI               = "Audi"
)

type Builder interface {
	Color(Color) Builder
	Automaker(Automaker) Builder
	TopSpeed(Speed) Builder
	Build() Interface
}

type Interface interface {
	Drive()
	Stop()
}

type Car struct {
	color     Color
	topSpeed  Speed
	automaker Automaker
}

func (c *Car) Drive() {
	panic("implement me")
}

func (c *Car) Stop() {
	panic("implement me")
}

func (c *Car) Automaker(aut Automaker) Builder {
	c.automaker = aut
	return c
}

func (c *Car) Color(col Color) Builder {
	c.color = col
	return c
}

func (c *Car) TopSpeed(spe Speed) Builder {
	c.topSpeed = spe
	return c
}

func (c *Car) Build() Interface {
	return c
}
```
