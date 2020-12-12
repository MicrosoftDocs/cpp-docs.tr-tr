---
description: 'Daha fazla bilgi edinin: TypeId Işleci'
title: typeid İşleci
ms.date: 10/04/2019
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: 8e036cbdcc540eca224b97b09d174362c454da6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145866"
---
# <a name="typeid-operator"></a>typeid İşleci

## <a name="syntax"></a>Syntax

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Açıklamalar

**`typeid`** İşleci, çalışma zamanında bir nesne türünün belirlenmesi için izin verir.

Sonucu **`typeid`** bir `const type_info&` . Değer, `type_info` hangi biçiminin kullanıldığına bağlı olarak, *türün tür kimliğini* veya *ifadenin* türünü temsil eden bir nesnesine başvurudur **`typeid`** . Daha fazla bilgi için bkz. [type_info sınıfı](../cpp/type-info-class.md).

**`typeid`** İşleç, yönetilen türlerle (soyut Bildirimciler veya örnekler) çalışmaz. Belirtilen bir türü alma hakkında daha fazla bilgi için <xref:System.Type> bkz. [TypeId](../extensions/typeid-cpp-component-extensions.md).

İşleci, çok **`typeid`** biçimli bir sınıf türünün l-değerine uygulandığında bir çalışma zamanı denetimi yapar, burada nesnenin true türü, girilen statik bilgilerle belirlenebilir. Bu gibi durumlar şunlardır:

- Bir sınıf başvurusu

- Bir işaretçi, başvurusu kaldırılmış `*`

- Alt simge işaretçisi ( `[ ]` ). (Çok biçimli bir tür işaretçisi olan bir alt simge kullanmak güvenli değildir.)

*İfade* bir temel sınıf türüne işaret ediyorsa, nesne gerçekten o temel sınıftan türetilmiş bir tür ise, `type_info` türetilmiş sınıf için bir başvuru oluşur. *İfade* , polimorfik bir türe (sanal işlevler içeren bir sınıf) işaret etmelidir. Aksi takdirde, sonucu `type_info` *ifadesinde* başvurulan statik sınıf için olur. Ayrıca, işaretçinin işaret ettiği bir nesne olması için işaretçiye başvurulmalıdır. İşaretçinin başvurusunu oluşturmadan, sonuç `type_info` işaretçi için, işaret ettiği şekilde değil, olur. Örneğin:

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

*İfadenin* bir işaretçinin başvurusu varsa ve bu işaretçinin değeri sıfır ise, **`typeid`** [bad_typeid bir özel durum](../cpp/bad-typeid-exception.md)oluşturur. İşaretçi geçerli bir nesneyi işaret etmez, bir `__non_rtti_object` özel durum oluşturulur. Nesne bir biçimde geçersiz olduğu için bir hata tetikleyen RTTı çözümleme girişimi olduğunu gösterir. (Örneğin, bu hatalı bir işaretçidir veya kod [/gr](../build/reference/gr-enable-run-time-type-information.md)ile derlenmedi).

*İfade* , nesnenin temel sınıfına bir başvuru değil, bir işaretçi değilse, sonuç `type_info` *ifadenin* statik türünü temsil eden bir başvurudur. Bir ifadenin *statik türü* , derleme zamanında bilinen bir ifadenin türüne başvurur. Yürütme semantikleri, bir ifadenin statik türü değerlendirilirken göz ardı edilir. Ayrıca, bir ifadenin statik türü belirlenirken, mümkün olduğunca başvurular da dikkate alınmaz:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**`typeid`** , şablon parametresinin türünü belirleyebilmek için de kullanılabilir:

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
