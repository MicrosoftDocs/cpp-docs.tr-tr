---
title: reinterpret_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 34c2fcb0e1f7f4df4e207d1737afc9c42e011feb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188291"
---
# <a name="reinterpret_cast-operator"></a>reinterpret_cast İşleci

Herhangi bir işaretçinin diğer işaretçi türlerine dönüştürülmesine izin verir. Ayrıca tüm integral türlerinin herhangi bir işaretçi türüne dönüştürülmesini sağlar ve tam tersi de geçerlidir.

## <a name="syntax"></a>Sözdizimi

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Açıklamalar

**Reinterpret_cast** işlecinin kötüye kullanımı kolayca güvenli bir şekilde yapılabilir. İstenen dönüştürme doğal olarak alt düzey değilse, diğer atama işleçlerinden birini kullanmalısınız.

**Reinterpret_cast** işleci `int*``char*` gibi dönüştürmeler için veya doğal olarak güvenli olmayan `Unrelated_class*``One_class*` için kullanılabilir.

**Reinterpret_cast** sonucu, özgün türüne geri dönüştürülenden başka hiçbir şey için güvenli bir şekilde kullanılamaz. Diğer kullanımlar, en iyi, taşınabilir olmayan.

**Reinterpret_cast** işleci **const**, **volatile**veya **__unaligned** özniteliklerinin üzerine atanamaz. Bu öznitelikleri kaldırma hakkında bilgi için bkz. [Const_cast işleci](../cpp/const-cast-operator.md) .

**Reinterpret_cast** işleci, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

**Reinterpret_cast** pratik kullanımı, bir değeri bir dizine eşleyen bir karma işlevdir, bu da iki farklı değerin aynı dizinle seyrek bir şekilde bitmesi için bir değer kullanır.

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

**Reinterpret_cast** , işaretçinin bir integral türü olarak işlenmesine izin verir. Sonuç daha sonra, benzersiz bir dizin (yüksek oranda olasılığa göre benzersiz) oluşturmak için bit kaydırılacağı ve kendisi ile XORed. Sonra bu dizin, işlevin dönüş türüne standart bir C stili atama ile kesilir.

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
