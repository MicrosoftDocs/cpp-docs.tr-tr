---
title: 'Lvalue başvuru bildirimci: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 595f2b683d2abb4cdc8a328dc6e86338ab90f214
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178073"
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue başvuru bildirimci: &amp;

Bir nesnenin adresini tutar, ancak sözdizimi bir nesne gibi davranır.

## <a name="syntax"></a>Sözdizimi

```
type-id & cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bir lvalue başvurusunu bir nesne için başka bir ad olarak düşünebilirsiniz. Bir lvalue başvuru bildirimi, bir başvuru bildirimci tarafından izlenen isteğe bağlı belirticilerden oluşur. Başvuru başlatılmalıdır ve değiştirilemez.

Adresi belirli bir işaretçi türüne dönüştürülebileceği herhangi bir nesne benzer başvuru türüne de dönüştürülebilir. Örneğin, adresi türüne dönüştürülebileceği herhangi bir nesne, `char &`türüne de dönüştürülebilir `char *`.

Başvuru bildirimlerini [Adres işlecinin](../cpp/address-of-operator-amp.md)kullanımıyla karıştırmayın. `&`*tanımlayıcı* önce **int** veya **char**gibi bir tür tarafından olduğunda, *tanımlayıcı* türe başvuru olarak belirtilir. `&`tanımlayıcısının önünde bir tür olmadığında kullanım, adres işlecinin bir *sıdır* .

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `Person` nesnesi ve bu nesneye bir başvuru bildirerek başvuru bildirimcisini gösterir. `rFriend`, `myFriend`bir başvuru olduğundan, her iki değişken de aynı nesneyi değiştirir.

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
[Başvuru Türü İşlev Bağımsız Değişkenleri](../cpp/reference-type-function-arguments.md)<br/>
[Başvuru Türü İşlev Dönüşleri](../cpp/reference-type-function-returns.md)<br/>
[İşaretçi Başvuruları](../cpp/references-to-pointers.md)
