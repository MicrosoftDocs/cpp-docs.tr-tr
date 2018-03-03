---
title: "reinterpret_cast işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- reinterpret_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0957a696d7675a932aa86531d39f2e4895ba1ff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast İşleci
Herhangi bir işaretçi türü dönüştürülecek hiçbir işaretçi sağlar. Ayrıca herhangi bir işaretçi türü ve tersi yönde dönüştürülecek herhangi bir tam sayı türü sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 B.internet `reinterpret_cast` işleci kolayca güvenli olabilir. İstenen dönüştürme kendiliğinden alt düzey olmadığı sürece, diğer atama işleçleri birini kullanmanız gerekir.  
  
 `reinterpret_cast` İşleci kullanılabilir dönüştürmelerde gibi `char*` için `int*`, veya `One_class*` için `Unrelated_class*`, doğası gereği güvenli olduğu.  
  
 Sonucunu bir `reinterpret_cast` özgün türüne cast dışında her şey için güvenli bir şekilde kullanılamaz. Diğer kullanımlar, en iyi nonportable.  
  
 `reinterpret_cast` İşleci olamaz atama dışarıda **const**, `volatile`, veya **__unaligned** öznitelikleri. Bkz: [const_cast işleci](../cpp/const-cast-operator.md) bu öznitelikler kaldırma hakkında bilgi için.  
  
 `reinterpret_cast` İşleci hedef türü null işaretçinin değeri boş işaretçi değeri dönüştürür.  
  
 Bir pratik kullanımını `reinterpret_cast` bir değer şekilde iki ayrı bir dizine hangi eşlemeleri değerleri nadiren son yukarı aynı dizinde bir karma işlevi olarak.  
  
```  
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
  
 `reinterpret_cast` İşaretçiyi ayrılmaz bir tür olarak kabul edilmesi izin verir. Sonuç sonra bit-kaydırılacağı uzaklık ve benzersiz bir dizin (benzersiz olasılığı yüksek derecede için) üretmek için kendi kendine XORed. Dizin, bir standart C işlevinin dönüş türü cast türü tarafından sonra kesilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)