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
ms.openlocfilehash: de716ec8c29bbdb50462cd6ea642ed603d411c2a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue başvuru Bildirimcisi: &amp;
Bir nesne adresini tutar ancak sözdizimsel olarak bir nesne gibi davranır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Lvalue başvuru bir nesne için başka bir ad olarak düşünebilirsiniz. Lvalue başvuru bildirimi isteğe bağlı bir başvuru bildirimcisi tarafından izlenen tanımlayıcıları listesinden oluşur. Bir başvuru başlatılması gerekir ve değiştirilemez.  
  
 Adresini verilen işaretçi türüne dönüştürülebilir herhangi bir nesne de benzer başvuru türüne dönüştürülebilir. Adresini türüne dönüştürülebilir Örneğin, herhangi bir nesne `char *` türüne dönüştürülebilir `char &`.  
  
 Başvuru bildirimleri kullanımı ile karıştırmayın [address-of işleci](../cpp/address-of-operator-amp.md). Zaman `&` *tanımlayıcısı* türüne göre gibi öncesinde `int` veya `char`, *tanımlayıcısı* bir başvuru türü olarak bildirilmiş. Zaman `&` *tanımlayıcısı* değil öncesinde türüne göre, address-of işleci kullanımdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bildirerek başvuru bildirimcisi gösterir bir `Person` nesne ve bu nesneye bir başvurusu. Çünkü `rFriend` başvurusudur `myFriend`, her iki değişken güncelleştirme aynı nesne değiştirir.  
  
```  
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