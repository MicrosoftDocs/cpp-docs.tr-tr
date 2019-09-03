---
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 8bbcecf95daeef6ea2d40877d37e0eb6b7f3a0e8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217089"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Microsoft 'a özgü**

Bellek erişim işlemlerini çağrı noktası boyunca yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
> `_ReadBarrier`, ,Ve`_ReadWriteBarrier`derleyici iç bilgileri ve makrokullanımdışıdırvekullanılmamalıdır.`MemoryBarrier` `_WriteBarrier` İş parçacıkları arası iletişim için [ C++ standart kitaplıkta](../standard-library/cpp-standard-library-reference.md)tanımlanan [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::\<atomik T >](../standard-library/atomic.md) gibi mekanizmalar kullanın. Donanım erişimi için, [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğini [geçici](../cpp/volatile-cpp.md) anahtar sözcüğüyle birlikte kullanın.

## <a name="syntax"></a>Sözdizimi

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç `_ReadBarrier` , çağrı noktasındaki bellek erişimi işlemlerini kaldırabilen veya yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
