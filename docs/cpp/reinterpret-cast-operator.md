---
title: reinterpret_cast işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- reinterpret_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18a7cdd80c1d7b6b17a988d8f3581c7757f69823
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948116"
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast İşleci
Herhangi bir işaretçi türü dönüştürülecek herhangi bir işaretçi sağlar. Ayrıca, herhangi bir işaretçi türü ve tersi dönüştürülecek herhangi bir tamsayı türü sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kötüye kullanımı **reinterpret_cast** işleci kolayca güvenli olabilir. İstenen dönüştürme kendiliğinden alt düzey olmadığı sürece, bir atama işleçleri birini kullanmanız gerekir.  
  
 **Reinterpret_cast** işleci kullanılabilir dönüştürmeler için gibi `char*` için `int*`, veya `One_class*` için `Unrelated_class*`, doğası gereği güvenli olduğu.  
  
 Sonucu bir **reinterpret_cast** özgün türüne atandığını dışında her şey için güvenli bir şekilde kullanılamaz. Diğer kullanımlar, en iyi nitelikte.  
  
 **Reinterpret_cast** işleci beklenmedik şekilde atayamaz **const**, **geçici**, veya **__unaligned** öznitelikleri. Bkz: [const_cast işleci](../cpp/const-cast-operator.md) bu öznitelikleri kaldırma hakkında bilgi için.  
  
 **Reinterpret_cast** işlecini bir null işaretçi değeri hedef türünün boş işaretçi değerine dönüştürür.  
  
 Bir pratik kullanımını **reinterpret_cast** hangi şekilde iki farklı bir dizin değeri eşler değerleri nadiren son yedekleme ile aynı dizine bir karma işlevi bulunmaktadır.  
  
```cpp 
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 **Reinterpret_cast** bir tam sayı türü olarak kabul edilmesi bir işaretçi sağlar. Sonuç ardından bit-kaydırılacağı uzaklık ve (benzersiz olasılığı yüksek derecede için) benzersiz bir dizin üretmek için kendi kendine XORed. Dizin, ardından tarafından döndürülen işlev türüne standart C stili kesilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)