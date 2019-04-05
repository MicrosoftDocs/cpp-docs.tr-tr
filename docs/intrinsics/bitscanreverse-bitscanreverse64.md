---
title: _BitScanReverse, _BitScanReverse64
ms.date: 11/04/2016
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
ms.openlocfilehash: 3639aac38f4c7df82cbbdb23ed9038ac86ba2cc0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59021976"
---
# <a name="bitscanreverse-bitscanreverse64"></a>_BitScanReverse, _BitScanReverse64

**Microsoft'a Özgü**

En az önemli bit (LSB'si) belirlenen bitin (1) için en anlamlı bit (MSB) maskesi verileri arayın.

## <a name="syntax"></a>Sözdizimi

```
unsigned char _BitScanReverse(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanReverse64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>Parametreler

*Dizin*<br/>
[out] Bulunan bit konumunu ilk set bit (1) ile yüklendi.

*Maskesi*<br/>
[in] Aranacak 32 bit veya 64-bit değeri.

## <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `Index` kümesi veya 0 biri ise hiçbir belirlenmiş bitleri bulunamadı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_BitScanReverse`|x86, ARM, x64|\<intrin.h >|
|`_BitScanReverse64`|ARM, x64||

## <a name="example"></a>Örnek

```
// BitScanReverse.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanReverse)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanReverse(&index, mask);
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
Mask: 12 Index: 3
```

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)