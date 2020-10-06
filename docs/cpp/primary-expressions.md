---
title: Birincil ifadeler
description: C++ programlama dilindeki birincil ifadeler.
ms.date: 10/02/2020
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 4c52992071453bc189a3078db9592b02dfb8ba9b
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765322"
---
# <a name="primary-expressions"></a>Birincil İfadeler

Birincil ifadeler daha karmaşık ifadelerin yapı taşlarıdır. Bunlar, kapsam çözümleme işleci () tarafından nitelenmiş sabit değerler, adlar ve adlar olabilir `::` . Birincil bir ifade aşağıdaki biçimlerden birini içerebilir:

*`primary-expression`*\
&emsp;*`literal`*\
&emsp;**`this`**\
&emsp;*`name`*\
&emsp;**`::`** *`name`* **`(`** *`expression`* **`)`**

*`literal`*, Sabit bir birincil ifadedir. Türü kendi belirtiminin biçimine bağlıdır. Değişmez değerler belirtme hakkında tüm bilgiler için bkz. [değişmez değerler](../cpp/numeric-boolean-and-pointer-literals-cpp.md) .

**`this`** Anahtar sözcüğü bir sınıf nesnesine yönelik bir işaretçidir. Statik olmayan üye işlevleri içinde kullanılabilir. İşlevin çağrıldığı sınıfının örneğine işaret eder. **`this`** Anahtar sözcüğü bir sınıf üye işlevinin gövdesi dışında kullanılamaz.

İşaretçinin türü, **`this`** `type * const` `type` işaretçiyi özel olarak değiştirolmayan işlevlerde (sınıf adıdır) **`this`** . Aşağıdaki örnek, üye işlev bildirimlerini ve türlerini gösterir **`this`** :

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

İşaretçinin türünü değiştirme hakkında daha fazla bilgi için **`this`** bkz. [ `this` işaretçi](this-pointer.md).

Kapsam çözümleme işleci () ve **`::`** ardından bir ad, birincil ifadedir.  Bu gibi adlar üye adları değil, genel kapsamdaki adlar olmalıdır. İfadenin türü, adın bildirimine göre belirlenir. Bu bir l değeridir (yani, bildirim adı bir l-değeri ise, atama ifadesinin sol tarafında görünebilir). Söz konusu ad geçerli kapsamda gizlenmiş olsa da, kapsam çözümleme işleci başvurulacak bir genel bir ad sağlar. Kapsam çözümleme işlecinin nasıl kullanılacağına ilişkin bir örnek için bkz. [kapsam](../cpp/scope-visual-cpp.md) .

Parantez içine alınmış bir ifade, birincil ifadedir. Türü ve değeri, parantez içinde olmayan ifadenin türü ve değeri ile aynıdır. Parantez içinde olmayan ifade bir l-değeri ise bu bir l değeridir.

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

Bu örneklerin hepsi, çeşitli formlarda ve bu şekilde birincil ifadeler *olarak kabul edilir*:

```cpp
MyClass // an identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>Ayrıca bkz.

[Ifade türleri](../cpp/types-of-expressions.md)
