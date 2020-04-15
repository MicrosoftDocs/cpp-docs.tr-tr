---
title: Kurucuları atamak (C++)
description: Diğer oluşturucuları çağırmak ve kod tekrarını azaltmak için C++'daki yasal yapıcıları kullanın.
ms.date: 11/19/2019
ms.openlocfilehash: f26a013aa3c081d900ffc3eb32649acc77505db0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316667"
---
# <a name="delegating-constructors"></a>Temsilci oluşturucuları

Birçok sınıfın benzer şeyler yapan birden çok oluşturucusu vardır(örneğin, parametreleri doğrulayın:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

Tüm doğrulamayı yapan bir işlev ekleyerek yinelenen kodu azaltabilirsiniz, ancak bir oluşturucu işin bir kısmını başka bir işleme devredebilirse, kodun anlaşılması ve bakımı daha kolay `class_c` olur. Delegating oluşturucular eklemek için `constructor (. . .) : constructor (. . .)` sözdizimini kullanın:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

Önceki örnekte adım attığınızda, yapıcının `class_c(int, int, int)` ilk olarak `class_c(int, int)`yapıcıyı çağırdığı `class_c(int)`ve sırayla çağıran . Her yapıcı, yalnızca diğer yapıcılar tarafından gerçekleştirilmeyen işi gerçekleştirir.

Çağrılan ilk oluşturucu nesneyi başharfe ait hale getirerek tüm üyelerinin bu noktada başlatılmasını ister. Burada gösterildiği gibi, başka bir kurucuya yetki veren bir oluşturucuda üye başlatma yapamazsınız:

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

Sonraki örnek, statik olmayan veri üyesi başlatılmasını gösterir. Bir oluşturucu da belirli bir veri üyesi nin başlatılması durumunda, üye başlatılması geçersiz kılınır dikkat edin:

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

Oluşturucu delegasyonu sözdizimi, constructor özyinelemesinin yanlışlıkla oluşturulmasını engellemez—Constructor1 Constructor1 çağırır Constructor1 çağırır—ve bir yığın taşma olana kadar hata yapılmaz. Döngülerden kaçınmak senin sorumluluğunda.

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```
