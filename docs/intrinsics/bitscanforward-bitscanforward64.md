---
title: _BitScanForward, _BitScanForward64
ms.date: 11/04/2016
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 8b09aeee485611ddd20d51b4c1e36ec98c03c26e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62264224"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Microsoft'a özgü**

Belirlenen bitin (1) için en önemli bite (MSB) (LSB'si) en az önemli bit maskesi verileri arayın.

## <a name="syntax"></a>Sözdizimi

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>Parametreler

*Index*<br/>
[out] Bulunan bit konumunu ilk set bit (1) ile yüklendi.

*Maskesi*<br/>
[in] Aranacak 32 bit veya 64-bit değeri.

## <a name="return-value"></a>Dönüş Değeri

Maske sıfırsa 0; sıfır olmayan Aksi takdirde.

## <a name="remarks"></a>Açıklamalar

Bit kümesinin bulunursa bit bulunan ilk belirlenen bitin konumunu ilk parametre olarak döndürülür. Bit kümesinin bulunması durumunda 0 döndürülür; Aksi takdirde, 1 döndürülür.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64|
|`_BitScanForward64`|ARM, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="example"></a>Örnek

```
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>Giriş

```
12
```

## <a name="sample-output"></a>Örnek Çıktı

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)