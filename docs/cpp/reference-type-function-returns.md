---
title: Başvuru Türü İşlev Dönüşleri
ms.date: 11/04/2016
helpviewer_keywords:
- function return types [C++], reference type
- data types [C++], function return types
- functions [C++], return types
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
ms.openlocfilehash: 5e84643713dcbcb278fe7ce07c5d55f3593ec2ef
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188304"
---
# <a name="reference-type-function-returns"></a>Başvuru Türü İşlev Dönüşleri

İşlevler, bir başvuru türü döndürmek için bildirilebilir. Böyle bir bildirim yapmanın iki nedeni vardır:

- Döndürülen bilgiler, bir başvuru döndürmenin bir kopya döndürmekten daha etkili olmasını sağlayacak kadar büyüktür.

- İşlevin türü l değeri olmalıdır.

- İşlevin döndürdüğü zaman başvurulan nesne kapsam dışına gidemeyecektir.

Büyük nesneleri işlevlerine göre işlevlere geçirmek daha verimli olacağından, aynı *zamanda işlevlerden başvuruya* göre *büyük nesneler döndürmek* daha verimli olabilir. Başvuru dönüş protokolü, nesneyi döndürülmeden önce geçici bir konuma kopyalama ihtiyacını ortadan kaldırır.

Başvuru dönüş türleri, işlevin bir l değeri olarak değerlendirilmesi gerektiğinde de kullanışlıdır. Çoğu aşırı yüklenmiş işleç, özellikle de atama işleci bu kategorinin kapsamındadır. Aşırı yüklenmiş işleçler, [aşırı yüklenmiş işleçlerle](../cpp/operator-overloading.md)ele alınmıştır.

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

## <a name="output"></a>Çıktı

```Output
x = 7
y = 9
```

`x` ve `y` işlevlerinin döndürülen başvuru türleri olarak bildirildiğine dikkat edin. Bu işlevler, atama deyiminin her iki tarafında da kullanılabilir.

Ayrıca Main 'de Point nesnesi kapsamda kalır ve bu nedenle başvuru üyeleri hala canlı olur ve güvenle erişilebilir.

Başvuru türlerinin bildirimleri, aşağıdaki durumlar dışında başlatıcılar içermelidir:

- Açık **extern** bildirimi

- Bir sınıf üyesinin bildirimi

- Bir sınıf içerisinde bildirim

- Bir işlevin bağımsız değişkeninin veya bir işlevin dönüş türünün bildirimi

## <a name="caution-returning-address-of-local"></a>Uyarı yerel adresinin döndürülmüştür

Yerel kapsamda bir nesne bildirirseniz, işlev döndüğünde bu nesne yok edilir. İşlev bu nesneye bir başvuru döndürürse, çağıran null başvuruyu kullanmayı denerse, bu başvuru çalışma zamanında erişim ihlaline neden olur.

```cpp
// C4172 means Don’t do this!!!
Foo& GetFoo()
{
    Foo f;
    ...
    return f;
} // f is destroyed here
```

Derleyici bu durumda bir uyarı verir: `warning C4172: returning address of local variable or temporary`. Basit programlarda, bellek konumunun üzerine yazılmadan önce başvuruya çağrı tarafından erişildiğinde hiçbir erişim ihlali gerçekleşmeyecektir. Bunun nedeni, bu durumla kaynaklanmaktadır. Uyarıyı önemseme.

## <a name="see-also"></a>Ayrıca bkz.

[Başvurular](../cpp/references-cpp.md)
