---
title: reinterpret_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 421a1fdce6834f800cd33a55d75c9dc4f88ffc93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463105"
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

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)