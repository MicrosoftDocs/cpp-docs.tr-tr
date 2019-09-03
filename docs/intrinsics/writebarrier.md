---
title: _WriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: a41f4c6c5cdd6b72e76a596622912e88fbd03f34
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219318"
---
# <a name="_writebarrier"></a>_WriteBarrier

**Microsoft 'a özgü**

Bellek erişim işlemlerini çağrı noktası boyunca yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
> `_ReadBarrier`, ,Ve`_ReadWriteBarrier`derleyici iç bilgileri ve makrokullanımdışıdırvekullanılmamalıdır.`MemoryBarrier` `_WriteBarrier` İş parçacıkları arası iletişim için, [ C++ standart kitaplıkta](../standard-library/cpp-standard-library-reference.md)tanımlanan [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::\<atomik T >](../standard-library/atomic.md)gibi mekanizmalar kullanın. Donanım erişimi için, [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğini [geçici](../cpp/volatile-cpp.md) anahtar sözcüğüyle birlikte kullanın.

## <a name="syntax"></a>Sözdizimi

```C
void _WriteBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç `_WriteBarrier` , çağrı noktasındaki bellek erişimi işlemlerini kaldırabilen veya yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_Readbariyer](../intrinsics/readbarrier.md)\
[_Readwriteengelini](../intrinsics/readwritebarrier.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
