---
description: 'Hakkında daha fazla bilgi edinin: __ll_lshift'
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 324286a0f7ca28eaa7259f05f629f87e763aac0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167766"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Microsoft'a Özgü**

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

## <a name="return-value"></a>Döndürülen değer

Maske, bitler tarafından sola `nBit` kaydırır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Programınızı 64 bitlik mimari için derlerseniz ve `nBit` 63 ' den büyükse, kaydırma yapılacak bit sayısı `nBit` mod 64 ' dir. Programınızı 32 bitlik mimari için derlerseniz ve `nBit` 31 ' den büyükse, kaydırma yapılacak bit sayısı `nBit` mod 32 ' dir.

`ll`Ad içinde, () üzerinde bir işlem olduğunu gösterir **`long long`** **`__int64`** .

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

## <a name="output"></a>Çıktı

```Output
10000
```

> [!NOTE]
> Sol kaydırma işleminin imzasız sürümü yok. Bunun nedeni `__ll_lshift` zaten işaretsiz bir giriş parametresi kullanıyor olması. Sağ SHIFT 'in aksine, sol SHIFT 'e ait imza bağımlılığı yoktur, çünkü sonuçdaki en az önemli bir bit, kaydırılan değerin işaretinden bağımsız olarak her zaman sıfır olarak ayarlanmıştır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__ll_rshift](../intrinsics/ll-rshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
