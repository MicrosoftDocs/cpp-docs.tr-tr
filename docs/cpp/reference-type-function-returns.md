---
title: Başvuru Türü İşlev Dönüşleri
ms.date: 11/04/2016
helpviewer_keywords:
- function return types [C++], reference type
- data types [C++], function return types
- functions [C++], return types
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
ms.openlocfilehash: a2d7fa9ddbc1d4a2f922b5a20930e150ae991f38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403444"
---
# <a name="reference-type-function-returns"></a>Başvuru Türü İşlev Dönüşleri

İşlevler, bir başvuru türü döndürmek için bildirilebilir. Böyle bir bildirim yapmanın iki nedeni vardır:

- Döndürülen bilgiler, bir başvuru döndürmenin bir kopya döndürmekten daha etkili olmasını sağlayacak kadar büyüktür.

- İşlevin türü l değeri olmalıdır.

- İşlevi döndüğünde başvurulan nesne kapsam dışına çıkmadan değil.

Büyük nesneler geçirilmesinin daha etkili olabilir gibi *için* işlevlerin başvuruya göre de olabilir büyük nesneler döndürmek için daha verimli *gelen* başvuru. Başvuru dönüş protokolü, nesneyi döndürülmeden önce geçici bir konuma kopyalama ihtiyacını ortadan kaldırır.

Başvuru dönüş türleri, işlevin bir l değeri olarak değerlendirilmesi gerektiğinde de kullanışlıdır. Çoğu aşırı yüklenmiş işleç, özellikle de atama işleci bu kategorinin kapsamındadır. Aşırı yüklenmiş işleçler kapsamdaki [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).

## <a name="example"></a>Örnek

Aşağıdaki `Point` örneğini göz önünde bulundurun:

```cpp
// refType_function_returns.cpp
// compile with: /EHsc

#include <iostream>
using namespace std;

class Point
{
public:
// Define "accessor" functions as
//  reference types.
unsigned& x();
unsigned& y();
private:
// Note that these are declared at class scope:
unsigned obj_x;
unsigned obj_y;
};

unsigned& Point :: x()
{
return obj_x;
}
unsigned& Point :: y()
{
return obj_y;
}

int main()
{
Point ThePoint;
// Use x() and y() as l-values.
ThePoint.x() = 7;
ThePoint.y() = 9;

// Use x() and y() as r-values.
cout << "x = " << ThePoint.x() << "\n"
<< "y = " << ThePoint.y() << "\n";
}
```

## <a name="output"></a>Çıkış

```Output
x = 7
y = 9
```

`x` ve `y` işlevlerinin döndürülen başvuru türleri olarak bildirildiğine dikkat edin. Bu işlevler, atama deyiminin her iki tarafında da kullanılabilir.

Ayrıca, ana Point nesne kapsam içinde kalır ve bu nedenle başvuru üyeleri hala etkin tutulan bağlantıyı destekliyorsa ve güvenli bir şekilde erişilebilir olduğunu unutmayın.

Başvuru türlerinin bildirimleri, aşağıdaki durumlar dışında başlatıcılar içermelidir:

- Açık **extern** bildirimi

- Bir sınıf üyesinin bildirimi

- Bir sınıf içerisinde bildirim

- Bir işlevin bağımsız değişkeninin veya bir işlevin dönüş türünün bildirimi

## <a name="caution-returning-address-of-local"></a>Uyarı yerel adresini döndürüyor

Yerel kapsamda bir nesne bildirirseniz, işlevi döndüğünde, nesne yok edilir. İşlev, bu nesneye bir başvuru döndürür, çağırana null başvuru kullanma girişiminde bulunursa, bu başvuruyu büyük olasılıkla çalışma zamanında bir erişim ihlali neden olur.

```cpp
// C4172 means Don’t do this!!!
Foo& GetFoo()
{
    Foo f;
    ...
    return f;
} // f is destroyed here
```

Derleyici, bu durumda bir uyarı verir: `warning C4172: returning address of local variable or temporary`. Basit programlarında bellek konumuna yazılır önce başvuru çağıran tarafından erişildiği durumda hiçbir erişim ihlali zaman zaman ortaya çıkar mümkündür. Çalıştırmaları Şanslar nedeni budur. Uyarı önemseyin.

## <a name="see-also"></a>Ayrıca bkz.

[Başvurular](../cpp/references-cpp.md)