---
title: Başvuru türü işlev dönüşleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function return types [C++], reference type
- data types [C++], function return types
- functions [C++], return types
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 867313625ccc90924eed0c0c9405970f2cb90f8a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="reference-type-function-returns"></a>Başvuru Türü İşlev Dönüşleri
İşlevler, bir başvuru türü döndürmek için bildirilebilir. Böyle bir bildirim yapmanın iki nedeni vardır:  
  
-   Döndürülen bilgiler, bir başvuru döndürmenin bir kopya döndürmekten daha etkili olmasını sağlayacak kadar büyüktür.  
  
-   İşlevin türü l değeri olmalıdır.  
  
-   İşlevi döndüğünde başvurulan nesne kapsam dışında gidin değil.  
  
 Büyük nesneleri geçirmek için daha etkili olabilir gibi *için* işlevlerin başvuruya göre de olabilir büyük nesneler döndürmeye daha verimli *gelen* işlevlerin başvuruya göre. Başvuru dönüş protokolü, nesneyi döndürülmeden önce geçici bir konuma kopyalama ihtiyacını ortadan kaldırır.  
  
 Başvuru dönüş türleri, işlevin bir l değeri olarak değerlendirilmesi gerektiğinde de kullanışlıdır. Çoğu aşırı yüklenmiş işleç, özellikle de atama işleci bu kategorinin kapsamındadır. Aşırı yüklenmiş işleçler ele alınmıştır [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki `Point` örneğini göz önünde bulundurun:  
  
```  
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
  
```  
x = 7  
y = 9  
```  
  
 `x` ve `y` işlevlerinin döndürülen başvuru türleri olarak bildirildiğine dikkat edin. Bu işlevler, atama deyiminin her iki tarafında da kullanılabilir.  
  
 Ayrıca ana, Point nesne kapsam içinde kalır ve bu nedenle başvuru üyeleri hala canlı ve güvenli bir şekilde erişilebilir olduğunu unutmayın.  
  
 Başvuru türlerinin bildirimleri, aşağıdaki durumlar dışında başlatıcılar içermelidir:  
  
-   Açık `extern` bildirimleri  
  
-   Bir sınıf üyesinin bildirimi  
  
-   Bir sınıf içerisinde bildirim  
  
-   Bir işlevin bağımsız değişkeninin veya bir işlevin dönüş türünün bildirimi  
  
## <a name="caution-returning-address-of-local"></a>Uyarı yerel adresini döndürüyor  
 Nesneyi yerel kapsamda bildirirseniz işlevi döndüğünde söz konusu nesne yok. İşlevi bu nesneye bir başvurusu döndürürse, çağıran null başvuru kullanma girişiminde bulunursa bu başvuruyu büyük olasılıkla çalışma zamanında bir erişim ihlali neden olur.  
  
```  
// C4172 means Don’t do this!!!  
Foo& GetFoo()  
{  
    Foo f;  
    ...  
    return f;  
} // f is destroyed here  
```  
  
 Bu durumda bir uyarı derleyici verir: `warning C4172: returning address of local variable or temporary`. Basit programlarda bellek konumuna yazılmadan önce başvuru çağıran tarafından erişiliyorsa hiçbir erişim ihlali zaman zaman ortaya çıkar mümkündür. Çalıştırmaları Şanslar nedeni budur. Uyarı önemseyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvurular](../cpp/references-cpp.md)