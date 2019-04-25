---
title: __ll_rshift
ms.date: 11/04/2016
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: e39f8fe797467569077dd24baf49670607915107
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263366"
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

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)