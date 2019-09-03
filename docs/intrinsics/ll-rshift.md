---
title: __ll_rshift
ms.date: 09/02/2019
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: ad17991d84acb7e531baf9435610ebd566197a22
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217493"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Microsoft 'a özgü**

İlk parametre tarafından belirtilen 64 bitlik bir değeri, ikinci parametre tarafından belirtilen bir bit sayısıyla sağa kaydırır.

## <a name="syntax"></a>Sözdizimi

```C
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Parametreler

*Maskesi*\
'ndaki Sağa kayılacak 64 bitlik tamsayı değeri.

*nBit*\
'ndaki Bit sayısı, x64 üzerindeki mod 64 ve x86 üzerinde mod 32.

## <a name="return-value"></a>Dönüş değeri

Bitler tarafından `nBit` kaydırılan maske.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İkinci parametre x64 üzerinde 64 ' den büyükse (x86 üzerinde 32), kaydırma yapılacak bit sayısını öğrenmek için bu sayı modül 64 (x86 üzerinde 32) alınır. Ön ek, 64 bitlik işaretli integral türü için `long long` `__int64`bir işlem, başka bir ad olduğunu gösterir. `ll`

## <a name="example"></a>Örnek

```cpp
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>Çıkış

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> `_ull_rshift` Kullanıldıysa, sağa kaydırılan değerin MSB değeri sıfır olur, bu nedenle istenen sonuç negatif bir değer söz konusu olduğunda elde edilmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
