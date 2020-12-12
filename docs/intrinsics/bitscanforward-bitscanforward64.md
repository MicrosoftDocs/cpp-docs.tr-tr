---
description: 'Hakkında daha fazla bilgi edinin: _BitScanForward _BitScanForward64'
title: _BitScanForward, _BitScanForward64
ms.date: 09/02/2019
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
ms.openlocfilehash: 182f22b5350fcad7c3da9a0d6f6df36c0871a3e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337226"
---
# <a name="_bitscanforward-_bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Microsoft'a Özgü**

Maske verilerinde en az önemli bit (LSB) ile küme bit (1) için en önemli bit (MSB) arasında arama yapın.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

### <a name="parameters"></a>Parametreler

*İndeks*\
dışı İlk küme bitinin (1) bulunduğu bit konumuyla yüklendi.

*Maskesi*\
'ndaki Aranacak 32-bit veya 64 bit değeri.

## <a name="return-value"></a>Döndürülen değer

maske sıfırsa 0; sıfır dışında tersi.

## <a name="remarks"></a>Açıklamalar

Bir küme bit bulunursa, bulunan ilk küme bitinin bit konumu ilk parametrede döndürülür. Ayarlanmış bir bit bulunamazsa 0 döndürülür; Aksi takdirde, 1 döndürülür.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64, ARM64|
|`_BitScanForward64`|ARM64, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="example"></a>Örnek

```cpp
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

```Input
12
```

```Output
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
