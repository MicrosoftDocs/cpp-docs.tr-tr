---
title: typeid İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: b1185f48df4a941eb2a5d81bfa67d07cdf4387d0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780892"
---
# <a name="typeid-operator"></a>typeid İşleci

## <a name="syntax"></a>Sözdizimi

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Açıklamalar

**TypeID** işleci, bir nesnenin çalışma zamanında belirlenecek türü sağlar.

Sonucu **TypeID** olduğu bir `const type_info&`. Değer bir başvurudur bir `type_info` temsil eden nesne *türü kimliği* veya türü *ifade*bağlı olarak hangi tür **TypeID** kullanılır. Bkz: [type_info sınıfı](../cpp/type-info-class.md) daha fazla bilgi için.

**TypeID** işleci yönetilen türlerle (soyut Bildirimciler veya örnekleri) çalışmaz, bkz: [TypeID](../extensions/typeid-cpp-component-extensions.md) alma hakkında bilgi <xref:System.Type> belirli bir türde.

**TypeID** işlecinin yaptığı bir l değeri olarak bir çok biçimli bir sınıf türünün uygulandığında bir çalışma zamanı denetimi burada sağlanan statik bilgilerle doğru nesne türü belirlenemiyor. Bu gibi durumlar şunlardır:

- Bir sınıf başvurusu

- İle Başvurusu kaldırılmış bir işaretçi \*

- Bir alt işaretçi (diğer bir deyişle [ ]). (Bir çok biçimli türün işaretçisi ile bir alt simge kullanmanın genellikle güvenli olmadığını unutmayın.)

Varsa *ifade* ancak nesne aslında o temel sınıftan türetilmiş bir tür değil bir temel sınıf türüne işaret eden bir `type_info` sonucu türetilmiş sınıf için başvuru. *İfade* çok biçimli bir türe (sanal işlevler içeren bir sınıf) işaret etmelidir. Aksi halde sonuç, `type_info` başvurulan statik sınıf için *ifade*. Ayrıca, işaretçinin işaret ettiği nesnenin kullanılabilmesi için işaretçinin başvurusu kaldırılmalıdır. İşaretçinin başvurusu kaldırılmazsa, sonuç olacaktır `type_info` işaretçisi değil işaret ettiği. Örneğin:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo.h>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

Varsa *ifade* bir işaretçinin başvurusunu kaldırıyorsa ve işaretçinin değeri sıfır ise **TypeID** oluşturur bir [bad_typeid özel durumu](../cpp/bad-typeid-exception.md). İşaretçi geçerli bir nesneye işaret etmiyorsa bir `__non_rtti_object` özel durumu oluşturulur, bir hata tetikleyen RTTI'yi analiz etmek için girişimini (erişim ihlali gibi), nesne şekilde geçersiz olduğundan (hatalı işaretçi veya kod derlenmediği ile[GR](../build/reference/gr-enable-run-time-type-information.md)).

Varsa *ifade* bir işaretçi ya da bir temel sınıf nesnenin bir başvuru değil sonucu olan bir `type_info` statik türünü temsil eden başvuru *ifade*. *Statik tür* derleme zamanında bilinen bir ifade, ifadenin türü gösterir. Yürütme semantikleri, bir ifadenin statik türü değerlendirilirken göz ardı edilir. Ayrıca, bir ifadenin statik türü belirlenirken, mümkün olduğunca başvurular da dikkate alınmaz:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**typeid** şablonlarında bir şablon parametresinin türünü belirlemek için de kullanılabilir:

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)