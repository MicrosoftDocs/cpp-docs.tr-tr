---
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: d755d045970da01d2eee33377c1452191eac4fe2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217979"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Microsoft 'a özgü**

Çağrı noktasındaki bellek erişimlerini yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
> `_ReadBarrier`, ,Ve`_ReadWriteBarrier`derleyici iç bilgileri ve makrokullanımdışıdırvekullanılmamalıdır.`MemoryBarrier` `_WriteBarrier` İş parçacıkları arası iletişim için, [ C++ standart kitaplıkta](../standard-library/cpp-standard-library-reference.md)tanımlanan [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::\<atomik T >](../standard-library/atomic.md)gibi mekanizmalar kullanın. Donanım erişimi için, [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğini [geçici](../cpp/volatile-cpp.md) anahtar sözcüğüyle birlikte kullanın.

## <a name="syntax"></a>Sözdizimi

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç `_ReadWriteBarrier` , çağrı noktasındaki bellek erişimlerini kaldırabilen veya yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_Readbariyer](../intrinsics/readbarrier.md)\
[_Writeengelini](../intrinsics/writebarrier.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
