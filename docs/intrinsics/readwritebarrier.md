---
title: _ReadWriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: a279017e57c8bf828b302940463bd0b3504f085d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626167"
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier

**Microsoft'a özgü**

Arama noktasındaki bellek erişimleri tekrar sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için gibi mekanizmaları kullanın [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md), içinde tanımlandığı [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_ReadWriteBarrier` İç sınırları kaldırabilir veya arama noktasındaki bellek erişimleri yeniden sıralama derleyici iyileştirmeleri.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_WriteBarrier](../intrinsics/writebarrier.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)