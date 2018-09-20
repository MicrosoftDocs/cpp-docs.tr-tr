---
title: __ll_rshift | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71e9d9ef844dc2f46b28129611b76214658327ee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374424"
---
# <a name="llrshift"></a>__ll_rshift

**Microsoft'a özgü**

İkinci parametre tarafından belirtilen bit sayısı sağa ilk parametre tarafından belirtilen 64-bit bir değer kaydırılır.

## <a name="syntax"></a>Sözdizimi

```
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>Parametreler

*Maskesi*<br/>
[in] Sağa kaydırmak için 64-bit tamsayı değeri.

*nBit*<br/>
[in] 64 x64 modül ve 32 x86 modül kaydırılacak bit sayısı.

## <a name="return-value"></a>Dönüş Değeri

Maske kaydırılacak tarafından `nBit` bitleri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

İkinci parametre numarası kaydırılacak bit sayısını belirlemek için 64 (32 x86) modül alınır (32) x86 x64 64'ten büyükse. `ll` Ön eki bu üzerinde bir işlem olduğunu gösterir `long long`, başka bir adı `__int64`, 64-bit imzalı tamsayı türü.

## <a name="example"></a>Örnek

```
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

```
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

**Not** varsa `_ull_rshift` olmuştur istenen sonuç negatif bir değer söz konusu olduğunda alındıktan değil şekilde kullanılan, Tamamlama sağa kaydırılacak değerin sıfır olacaktı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)