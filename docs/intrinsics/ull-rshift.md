---
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: e914a019877482058c6b2842d3138cda02f1e228
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219711"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Microsoft 'a özgü**

x64 üzerinde, ilk parametre tarafından belirtilen 64 bitlik bir değeri ikinci parametre tarafından belirtilen bir bit sayısıyla sağa kaydırır.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask, 
   int nBit
);
```

### <a name="parameters"></a>Parametreler

*maskesi*\
'ndaki Sağa kayılacak 64 bitlik tamsayı değeri.

*nBit*\
'ndaki Bit sayısı, x86 üzerindeki mod 32 ve x64 üzerinde mod 64.

## <a name="return-value"></a>Dönüş değeri

Bitler tarafından `nBit` kaydırılan maske.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İkinci parametre x86 üzerinde 31 ' den büyükse (x64 üzerinde 63), kaydırma yapılacak bit sayısını öğrenmek için bu sayı modül 32 (x64 üzerinde 64) olarak alınır. Ad içindeki ' i gösterir `unsigned long long (unsigned __int64)`. `ull`

## <a name="example"></a>Örnek

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshıft](../intrinsics/ll-rshift.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
