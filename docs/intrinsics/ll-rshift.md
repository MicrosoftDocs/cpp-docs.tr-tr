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
ms.openlocfilehash: 6ae750f1a8825096ee30adb01768d5603ab23a01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219670"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Microsoft'a Özgü**

İlk parametre tarafından belirtilen 64 bitlik bir değeri, ikinci parametre tarafından belirtilen bir bit sayısıyla sağa kaydırır.

## <a name="syntax"></a>Söz dizimi

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

## <a name="return-value"></a>Döndürülen değer

Bitler tarafından kaydırılan maske `nBit` .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İkinci parametre x64 üzerinde 64 ' den büyükse (x86 üzerinde 32), kaydırma yapılacak bit sayısını öğrenmek için bu sayı modül 64 (x86 üzerinde 32) alınır. `ll`Ön ek, **`long long`** **`__int64`** 64 bitlik işaretli integral türü için bir işlem, başka bir ad olduğunu gösterir.

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

## <a name="output"></a>Çıktı

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> `_ull_rshift`Kullanıldıysa, sağa kaydırılan değerin MSB değeri sıfır olur, bu nedenle istenen sonuç negatif bir değer söz konusu olduğunda elde edilmez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
