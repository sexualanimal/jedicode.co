---
layout:     post
title:      SOLID простым языком
date:       2018-10-24 17:04:10
summary:    Тут я попытаюсь максимально просто и в тот же момент максимально информативно вам пояснить что же такое SOLID и почему вам его нужно знать.
categories: java base
---

**SOLID** - акроним, который описывает пять дизайн принципов программирования, каждый из которых является разьяснением 
того как нужно писать код, это своего рода набо правил, которые стоит не только заучить но и понимать.

Если до этого момента вы небыли знакомы с SOLID то после их изучения вы поймете что и раньше вы уже использовали 
пускай не все но часть из них не понимая этого.

### SRP - Single Responsibility Principle

Это превый принцып говорит о том что класс или же интерфейс должен иметь одно назначение тоесть решать одну поставленую задачу.

***Что даст вам этот принцип?***

Вы получите то, что является золотым граалем в програмировании, а именно **слабосвязаный код**, так как каждый ваш класс будет отвечать за решение определенной задачи, и такое явление как мадификация логики вашего класса не потянет за собой ряд других исправлений других классов.

Это достигается путем соблюдения SRP на протяжении всего жизненого цикла проекта.

> *Также важно помнить, что создав класс или интерфейс который был предназначен для решения одной конкретной задачи соблюдая SRP со времением в результате роста функциональности может нарушить этот принцип.* 

Поэтму важно следить за всеми изменениями в коде и не допускать этого путем разделения бизнес-логики на два отдельных класса. И чтобы не упустить такие моменты на проекте должен пристуствовать **анализатор кода** и **код ревью**.

### OCP - Open/Closed Prociple

Означает то что вы должны давать возможность только разширять ваши классы но не давать возможности модифицировать его существующее поведение.

Чаще всего нарушение этого принципа вчтречается при использовании наследования где путем переопределения в наследнике можно модифицировать базовое поведение родительского класса.

Придерживаясь этого принципа конкретно в Java можно с помощью ключевого слова `final` который запретит дальнейшей модикации метода или же свойства класса.

###LSP - Liskov Substitution Principle

Создавая наследников одного и тогоже интерфейса или абстрактного класса они не должны менять поведения базового класса. Тоесть имея две реализации **B** и **C** класса **A** мы можем с легкость менять реализации и получать одинаковое конечное поведение обоих реализаций.

1) base type

```java
class Sample extends Base {
    private String name;
  
	public Sample() {
        super();
    }
}
```

### Code, with syntax highlighting

Here's an example of some ruby code with line anchors.

{% highlight ruby lineanchors %}
# The most awesome of classes
class Awesome < ActiveRecord::Base
  include EvenMoreAwesome

  validates_presence_of :something
  validates :email, email_format: true

  def initialize(email, name = nil)
    self.email = email
    self.name = name
    self.favorite_number = 12
    puts 'created awesomeness'
  end

  def email_format
    email =~ /\S+@\S+\.\S+/
  end
end
{% endhighlight %}

Here's some CSS:

{% highlight css %}
.foobar {
  /* Named colors rule */
  color: tomato;
}
{% endhighlight %}

Here's some JavaScript:

{% highlight js %}
var isPresent = require('is-present')

module.exports = function doStuff(things) {
  if (isPresent(things)) {
    doOtherStuff(things)
  }
}
{% endhighlight %}

Here's some HTML:

{% highlight html %}
<div class="m0 p0 bg-blue white">
  <h3 class="h1">Hello, world!</h3>
</div>
{% endhighlight %}



### ISP - Interface Segregation Principle

Description ...

### Dependecy Injection Principle

Description ...