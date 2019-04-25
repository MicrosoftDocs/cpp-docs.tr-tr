---
title: 'Lvalue başvuru Bildirimcisi: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 7710b6f1efc2de770b26ad50923bde2ee5200f61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209560"
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue başvuru Bildirimcisi: &amp;

Bir nesnenin adresini tutar ancak sözdizimsel olarak bir nesne gibi davranır.

## <a name="syntax"></a>Sözdizimi

```
type-id & cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bir lvalue başvurusu bir nesnenin başka bir ad olarak düşünebilirsiniz. İsteğe bağlı bir liste belirleyicilerinin bir başvuru bildirimcisi tarafından izlenen bir lvalue başvurusu bildirimi oluşur. Bir başvuru başlatılmalıdır ve değiştirilemez.

Herhangi bir nesnenin adresini verilen işaretçi türüne dönüştürülebilir benzer bir başvuru türüne de dönüştürülebilir. Örneğin, tüm nesne adresini türüne dönüştürülebilir `char *` türüne de dönüştürülebilir `char &`.

Başvuru bildirimleri kullanımı ile karıştırmayın [address-of işleci](../cpp/address-of-operator-amp.md). Zaman `&` *tanımlayıcı* gibi bir tür tarafından öncesinde **int** veya **char**, *tanımlayıcı* bir başvuru olarak bildirilir türü. Zaman `&` *tanımlayıcı* değil öncesinde bir tarafından kullanım, address-of işleci türüdür.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bildirerek başvuru bildirimcisi gösterir bir `Person` nesne ve o nesnenin bir başvuru. Çünkü `rFriend` bir başvurudur `myFriend`, güncelleştirme ya da değişken aynı nesneye değiştirir.

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