---
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 158ecbf39320d70b51f1f498a0b689ba58fec363
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221816"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Microsoft 'a özgü**

Sağlanan 64 bitlik değeri belirtilen bit sayısı ile sola kaydırır.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Parametreler

*Maskesi*\
'ndaki Sola kayılacak 64 bitlik tamsayı değeri.

*nBit*\
'ndaki Kaydırılacak bit sayısı.

## <a name="return-value"></a>Dönüş değeri

Maske, bitler tarafından `nBit` sola kaydırır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Programınızı 64 bitlik mimari için derlerseniz ve `nBit` 63 ' den büyükse, kaydırma yapılacak bit sayısı mod 64 ' dir. `nBit` Programınızı 32 bitlik mimari için derlerseniz ve `nBit` 31 ' den büyükse, kaydırma yapılacak bit sayısı mod 32 ' dir. `nBit`

Ad `ll` içinde, (`__int64`) üzerinde `long long` bir işlem olduğunu gösterir.

## <a name="example"></a>Örnek

```cpp
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>Çıkış

```Output
10000
```

> [!NOTE]
> Sol kaydırma işleminin imzasız sürümü yok. Bunun nedeni `__ll_lshift` zaten işaretsiz bir giriş parametresi kullanıyor olması. Sağ SHIFT 'in aksine, sol SHIFT 'e ait imza bağımlılığı yoktur, çünkü sonuçdaki en az önemli bir bit, kaydırılan değerin işaretinden bağımsız olarak her zaman sıfır olarak ayarlanmıştır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__ll_rshıft](../intrinsics/ll-rshift.md)\
[__ull_rshıft](../intrinsics/ull-rshift.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
