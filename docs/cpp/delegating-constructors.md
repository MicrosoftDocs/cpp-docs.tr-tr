---
title: Temsilci oluşturucuları (C++)
description: Diğer oluşturucuları çağırmak ve C++ kod tekrarını azaltmak için ' de temsilci seçme oluşturucuları kullanın.
ms.date: 11/19/2019
ms.openlocfilehash: 533cdfbeb882f3770cc554b0633611a4ffc2cfbd
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74250676"
---
# <a name="delegating-constructors"></a>Temsilci oluşturucuları

Birçok sınıfta benzer şeyler yapan birden çok Oluşturucu vardır — örneğin, parametreleri doğrula:

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

Tüm doğrulamayı yapan bir işlev ekleyerek yinelenen kodu azaltabilirsiniz, ancak `class_c` kodun bir oluşturucunun bir kısmını başka bir Oluşturucu için temsilci seçip sürdürmesinin daha kolay anlaşılması ve korunması daha kolay olabilir. Temsilci oluşturucuları eklemek için `constructor (. . .) : constructor (. . .)` sözdizimini kullanın:

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

Önceki örnekte yaptığınız gibi, oluşturucunun `class_c(int, int, int)` ilk olarak Oluşturucu `class_c(int, int)`çağırdığına dikkat edin, bu da `class_c(int)`çağırır. Kurucuların her biri yalnızca diğer oluşturucular tarafından gerçekleştirilmeyen işleri gerçekleştirir.

Çağrılan ilk Oluşturucu nesnesini, tüm üyelerinin o noktada başlatılması için başlatır. Burada gösterildiği gibi, başka bir oluşturucuya temsilci olan bir oluşturucuda üye başlatma yapamazsınız:

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

Sonraki örnekte, statik olmayan veri üyesi başlatıcıların kullanımı gösterilmektedir. Bir oluşturucunun belirli bir veri üyesini de başlattığında üye başlatıcısı geçersiz kılındığına dikkat edin:

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

Oluşturucu temsili sözdizimi, Oluşturucu özyineleme yanlışlıkla oluşturulmasını engellemez — constructor1, constructor1 çağıran Constructor2 çağırır ve yığın taşması olana kadar hiçbir hata oluşturulmaz. Döngüleriniz ortadan kaldırmak sizin sorumluluğunuzdadır.

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
