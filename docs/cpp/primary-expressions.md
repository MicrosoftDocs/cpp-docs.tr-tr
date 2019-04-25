---
title: Birincil İfadeler
ms.date: 11/04/2016
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: e7dcb8290c0130fa9376e48f065e82163a1ca5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312316"
---
# <a name="primary-expressions"></a>Birincil İfadeler

Birincil ifadeler daha karmaşık ifadelerin yapı taşlarıdır. Oldukları değişmez değerleri, adlar ve kapsam çözümleme işleci tarafından belirtilen adlardır (`::`).  Birincil bir ifade aşağıdaki biçimlerden birini içerebilir:

```
literal
this
name
::name ( expression )
```

A *değişmez değer* sabit bir birincil ifadedir. Türü kendi belirtiminin biçimine bağlıdır. Bkz: [değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md) değişmez değerleri belirtme hakkında tam bilgi için.

**Bu** anahtar sözcüğü bir sınıf nesnesine bir işaretçidir. Statik olmayan üye işlevlerinde kullanılabilir ve işlevin çağrıldığı sınıfın örneğini gösterir. **Bu** anahtar sözcüğü bir sınıf işlevi üyesinin gövdesi dışında kullanılamaz.

Türünü **bu** işaretçisi `type`  **\*const** (burada `type` sınıf adıdır) özel olarak değiştirmeyen işlevler içindeki **bu** işaretçi. Aşağıdaki örnek üye işlev bildirimlerini ve türlerini gösterir **bu**:

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

Bkz: [this işaretçisi](this-pointer.md) türünü değiştirme hakkında daha fazla bilgi için **bu** işaretçi.

Kapsam çözümleme işleci (`::`) arkasından bir ad birincil bir ifade oluşturur.  Bu gibi adlar üye adları değil, genel kapsamdaki adlar olmalıdır.  Bu ifadenin türü adın bildirimi tarafından belirlenir. Bildirim adı lvalue ise, bu bir lvalue olur (diğer bir deyişle, bir atama işleci ifadesinin sol tarafında görünebilir). Söz konusu ad geçerli kapsamda gizlenmiş olsa da, kapsam çözümleme işleci başvurulacak bir genel bir ad sağlar. Bkz: [kapsam](../cpp/scope-visual-cpp.md) kapsam çözümleme işleci ile kullanma örneği için.

Parantez içine alınmış bir ifade, türü ve değeri parantez içinde olmayan ifadelerle aynı olan birincil bir ifadedir. Parantez içinde olmayan bir ifade bir lvalue ise, bu bir l-value olur.

Birincil ifadenin örnekleri şunlardır:

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

Aşağıdaki örneklerde tüm değerlendirilir *adları*ve bu nedenle birincil ifadeler çeşitli biçimlerde:

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)