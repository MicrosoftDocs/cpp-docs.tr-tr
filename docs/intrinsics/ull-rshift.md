---
title: __ull_rshift
ms.date: 11/04/2016
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: fee48cc731331e7cb427bc880d84ae07cc8ed9c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521310"
---
# <a name="ullrshift"></a>__ull_rshift

**Microsoft'a özgü**

x64 üzerinde ikinci parametre tarafından belirtilen bit sayısı sağa ilk parametre tarafından belirtilen 64-bit bir değer geçirir.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __ull_rshift( 
   unsigned __int64 mask,  
   int nBit 
);
```

#### <a name="parameters"></a>Parametreler

*Maskesi*<br/>
[in] Sağa kaydırmak için 64-bit tamsayı değeri.

*nBit*<br/>
[in] Modül x86 32 ve 64 x64 modül kaydırmak için bit sayısı.

## <a name="return-value"></a>Dönüş Değeri

Maske kaydırılacak tarafından `nBit` bitleri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

İkinci parametre x86 (x64 63) 31 daha büyükse, numara 32 (64 x64) modül kaydırılacak bit sayısını belirlemek için alınır. `ull` Adlarında gösterir `unsigned long long (unsigned __int64)`.

## <a name="example"></a>Örnek

```
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

## <a name="output"></a>Çıkış

```
1
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)