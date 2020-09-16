---
title: _InterlockedAdd iç işlevler
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
ms.openlocfilehash: efe1444273f17c8f0544d2c51b98923169032e61
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683903"
---
# <a name="_interlockedadd-intrinsic-functions"></a>_InterlockedAdd iç işlevler

**Microsoft'a Özgü**

Bu işlevler, birden fazla iş parçacığının paylaşılan bir değişkene erişimi olduğunda işlemin başarılı bir şekilde tamamlanmasını sağlayan atomik bir ekleme yapar.

## <a name="syntax"></a>Söz dizimi

```C
long _InterlockedAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_rel(
   long volatile * Addend,
   long Value
);
__int64 _InterlockedAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_nf (
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
```

### <a name="parameters"></a>Parametreler

*Doğrusal formülündeki toplanan*\
[in, out] Eklenecek tamsayı işaretçisi; ekleme sonucuyla değiştirilmiştir.

*Deeri*\
'ndaki Eklenecek değer.

## <a name="return-value"></a>Döndürülen değer

Her iki işlev de eklemenin sonucunu döndürür.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_InterlockedAdd`|ARM, ARM64|
|`_InterlockedAdd_acq`|ARM, ARM64|
|`_InterlockedAdd_nf`|ARM, ARM64|
|`_InterlockedAdd_rel`|ARM, ARM64|
|`_InterlockedAdd64`|ARM, ARM64|
|`_InterlockedAdd64_acq`|ARM, ARM64|
|`_InterlockedAdd64_nf`|ARM, ARM64|
|`_InterlockedAdd64_rel`|ARM, ARM64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Veya sonekleri olan bu işlevlerin sürümleri, `_acq` bir veya daha fazla `_rel` alma ve yayınlama semantiğini elde eden bir toplama işlemi gerçekleştirir. *Alma semantiği* , işlemin sonucunun sonraki bellek okuma ve yazma işlemleri öncesinde tüm iş parçacıkları ve işlemciler için görünür hale getirilme anlamına gelir. Alma, kritik bir bölüm girerken faydalıdır. *Sürüm semantiği* , tüm bellek okuma ve yazma işlemlerinin, işlemin sonucu görünür hale gelmeden önce tüm iş parçacıkları ve işlemcilere görünür hale getirilmesidir. Yayın, kritik bir bölümden ayrıldığınızda yararlıdır. `_nf`("Sınır olmayan") son ek olan iç bilgiler bellek engeli olarak davranmaz.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="examples"></a>Örnekler

```cpp
// interlockedadd.cpp
// Compile with: /Oi /EHsc
// processor: ARM
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAdd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FF0000;
        long retval;
        retval = _InterlockedAdd(&data1, data2);
        printf("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

## <a name="output"></a>Çıkış

```Output
0xffffff00 0xff0000 0xffffff00
```

```cpp
// interlockedadd64.cpp
// compile with: /Oi /EHsc
// processor: ARM
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_InterlockedAdd64)

int main()
{
        __int64 data1 = 0x0000FF0000000000;
        __int64 data2 = 0x00FF0000FFFFFFFF;
        __int64 retval;
        cout << hex << data1 << " + " << data2 << " = " ;
        retval = _InterlockedAdd64(&data1, data2);
        cout << data1 << endl;
        cout << "Return value: " << retval << endl;
}
```

## <a name="output"></a>Çıkış

```Output
ff0000000000 + ff0000ffffffff = ffff00ffffffff
Return value: ffff00ffffffff
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
