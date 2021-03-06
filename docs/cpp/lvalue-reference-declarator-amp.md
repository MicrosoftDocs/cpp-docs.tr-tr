---
description: 'Şu konuda daha fazla bilgi edinin: lvalue başvuru bildirimci: &amp;'
title: 'Lvalue başvuru bildirimci: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 99160f0eac10922e95b131d4246f898b3f59705e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312286"
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue başvuru bildirimci: &amp;

Bir nesnenin adresini tutar, ancak sözdizimi bir nesne gibi davranır.

## <a name="syntax"></a>Syntax

```
type-id & cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bir lvalue başvurusunu bir nesne için başka bir ad olarak düşünebilirsiniz. Bir lvalue başvuru bildirimi, bir başvuru bildirimci tarafından izlenen isteğe bağlı belirticilerden oluşur. Başvuru başlatılmalıdır ve değiştirilemez.

Adresi belirli bir işaretçi türüne dönüştürülebileceği herhangi bir nesne benzer başvuru türüne de dönüştürülebilir. Örneğin, adresi türüne dönüştürülebileceği herhangi bir nesne, `char *` türüne de dönüştürülebilir `char &` .

Başvuru bildirimlerini [Adres işlecinin](../cpp/address-of-operator-amp.md)kullanımıyla karıştırmayın. `&` *Tanımlayıcı* , veya gibi bir tür tarafından önce olduğunda, **`int`** tanımlayıcı, **`char`** türü  için bir başvuru olarak bildirilmiştir. `&` *Tanımlayıcının* önünde bir tür olmadığında kullanım, adres işlecinin olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, başvuru bildirimcisini bir `Person` nesne ve bu nesneye bir başvuru bildirerek gösterir. `rFriend`, Öğesine bir başvuru olduğundan `myFriend` , değişkenin güncelleştirilmesi aynı nesneyi değiştirir.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>Ayrıca bkz.

[Başvurular](../cpp/references-cpp.md)<br/>
[Başvuru türü Işlev bağımsız değişkenleri](../cpp/reference-type-function-arguments.md)<br/>
[Başvuru türü Işlev dönüşleri](../cpp/reference-type-function-returns.md)<br/>
[Işaretçilere başvurular](../cpp/references-to-pointers.md)
