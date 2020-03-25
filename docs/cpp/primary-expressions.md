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
ms.openlocfilehash: 03f0d0d04ad8ef2b052b9303d15437c53369a003
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177631"
---
# <a name="primary-expressions"></a>Birincil İfadeler

Birincil ifadeler daha karmaşık ifadelerin yapı taşlarıdır. Bunlar, kapsam çözümleme işleci (`::`) tarafından nitelenmiş sabit değerler, adlar ve adlardır.  Birincil bir ifade aşağıdaki biçimlerden birini içerebilir:

```
literal
this
name
::name ( expression )
```

Sabit *değer* sabit bir birincil ifadedir. Türü kendi belirtiminin biçimine bağlıdır. Değişmez değerler belirtme hakkında ayrıntılı bilgi için bkz. [değişmez değerler](../cpp/numeric-boolean-and-pointer-literals-cpp.md) .

**This** anahtar sözcüğü bir sınıf nesnesine yönelik bir işaretçidir. Statik olmayan üye işlevlerinde kullanılabilir ve işlevin çağrıldığı sınıfın örneğini gösterir. **Bu** anahtar sözcük, bir sınıf üye işlevinin gövdesi dışında kullanılamaz.

**Bu** işaretçinin türü, **Bu** işaretçiyi özellikle değiştirmekte olmayan işlevler içindeki const (`type` sınıf adı) `type` **\*** . Aşağıdaki örnek, üye işlev bildirimlerini ve **bunun**türlerini gösterir:

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

**Bu** işaretçinin türünü değiştirme hakkında daha fazla bilgi Için [Bu işaretçiye](this-pointer.md) bakın.

Bir ad tarafından izlenen kapsam çözümleme işleci (`::`), birincil bir ifade oluşturur.  Bu gibi adlar üye adları değil, genel kapsamdaki adlar olmalıdır.  Bu ifadenin türü adın bildirimi tarafından belirlenir. Bildirim adı lvalue ise, bu bir lvalue olur (diğer bir deyişle, bir atama işleci ifadesinin sol tarafında görünebilir). Söz konusu ad geçerli kapsamda gizlenmiş olsa da, kapsam çözümleme işleci başvurulacak bir genel bir ad sağlar. Kapsam çözümleme işlecinin nasıl kullanılacağına ilişkin bir örnek için bkz. [kapsam](../cpp/scope-visual-cpp.md) .

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

Aşağıdaki örneklerde, çeşitli formlarda *adlar*ve bu nedenle birincil ifadeler verilmiştir:

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
