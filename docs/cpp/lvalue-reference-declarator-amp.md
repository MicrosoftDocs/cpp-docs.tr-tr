---
title: 'Lvalue başvuru Bildirimcisi: &amp; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d16ed882b1037123963f105b1a78bf8e1023d332
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948221"
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuruları](../cpp/references-cpp.md)   
 [Başvuru türü işlev bağımsız değişkenleri](../cpp/reference-type-function-arguments.md)   
 [Başvuru türü işlev dönüşleri](../cpp/reference-type-function-returns.md)   
 [İşaretçi Başvuruları](../cpp/references-to-pointers.md)