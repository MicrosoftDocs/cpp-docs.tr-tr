---
title: typeid İşleci
ms.date: 10/04/2019
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: 93a2d3c494cd5aadafedcaaae9ec72809d633a4a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998753"
---
# <a name="typeid-operator"></a>typeid İşleci

## <a name="syntax"></a>Sözdizimi

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Açıklamalar

**TypeId** işleci, çalışma zamanında bir nesne türünün belirlenmesi için izin verir.

**TypeId** 'nin sonucu bir `const type_info&` ' dir. Değer, hangi **TypeId** biçiminin kullanıldığına bağlı olarak, *tür-kimliği* veya *ifadenin*türünü temsil eden `type_info` nesnesine bir başvurudur. Daha fazla bilgi için bkz. [type_info Class](../cpp/type-info-class.md).

**TypeId** işleci yönetilen türlerle (soyut Bildirimciler veya örnekler) çalışmaz. Belirtilen türde <xref:System.Type> alma hakkında bilgi için bkz. [TypeId](../extensions/typeid-cpp-component-extensions.md).

**TypeId** işleci, nesnenin true türünün belirtilen statik bilgilerle belirlenemediği, çok biçimli bir sınıf türünün l değerine uygulandığında bir çalışma zamanı denetimi yapar. Bu gibi durumlar şunlardır:

- Bir sınıf başvurusu

- Bir işaretçi, @no__t ile başvurulduğunu-0

- Alt simge işaretçisi (`[ ]`). (Çok biçimli bir tür işaretçisi olan bir alt simge kullanmak güvenli değildir.)

*İfade* bir temel sınıf türüne işaret ediyorsa, ancak nesne gerçekten o temel sınıftan türetilmiş bir tür ise, türetilmiş sınıf için `type_info` başvurusu elde edilir. *İfade* , polimorfik bir türe (sanal işlevler içeren bir sınıf) işaret etmelidir. Aksi takdirde sonuç, *ifadede*başvurulan statik sınıf için `type_info` ' dır. Ayrıca, işaretçinin işaret ettiği bir nesne olması için işaretçiye başvurulmalıdır. İşaretçinin başvurusunu oluşturmadan sonuç, işaretçinin işaret ettiği, işaretçi için `type_info` olur. Örneğin:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo>

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

*İfadenin* bir işaretçinin başvurusu varsa ve bu işaretçinin değeri sıfırsa, **TypeId** bir [bad_typeid özel durumu](../cpp/bad-typeid-exception.md)oluşturur. İşaretçi geçerli bir nesneye işaret vermezse, `__non_rtti_object` özel durumu oluşturulur. Nesne bir biçimde geçersiz olduğu için bir hata tetikleyen RTTı çözümleme girişimi olduğunu gösterir. (Örneğin, bu hatalı bir işaretçidir veya kod [/gr](../build/reference/gr-enable-run-time-type-information.md)ile derlenmedi).

*İfade* , nesnenin temel sınıfına bir başvuru değil, bir işaretçi değilse sonuç, *ifadenin*statik türünü temsil eden bir `type_info` başvurusudur. Bir ifadenin *statik türü* , derleme zamanında bilinen bir ifadenin türüne başvurur. Yürütme semantikleri, bir ifadenin statik türü değerlendirilirken göz ardı edilir. Ayrıca, bir ifadenin statik türü belirlenirken, mümkün olduğunca başvurular da dikkate alınmaz:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**TypeId** , şablon parametresinin türünü belirleyebilmek için şablonlarda de kullanılabilir:

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

[Çalışma zamanı tür bilgileri](../cpp/run-time-type-information.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
