# FactoryMethod

 GOF 디자인 패턴 3번째

 FactoryMethod는 하나의 class로 부터 파생된 여러 타입을 인자값에 따라 다르게 생산하는 `method`이다.

```cpp
class PizzaStore
{
public:
  Pizza makePizza(PizzaType type)
  {
    Pizza* pizza;
    switch(type)
    {
        case Pineapple:
          pizza = new PineapplePizza();
          break;
        case Pepperoni:
          pizza = new PepperoniPizza();
          break;
        case Potato:
          pizza = new PotatoPizza();
          break;
    }
    return pizza;
  }
};
```

 FactoryMethod를 사용시 다른 곳에서 `Pizza의 subtype`이 생성되는 것을 최소화하여, Superclas의 의존성을 낮춘다.
