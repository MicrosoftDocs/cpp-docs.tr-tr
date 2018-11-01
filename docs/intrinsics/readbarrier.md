---
title: _ReadBarrier
ms.date: 11/04/2016
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: d898f85398fffa79a9b484f0f82343b1675b61e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565171"
---
# <a name="readbarrier"></a>_ReadBarrier

**Microsoft'a özgü**

Arama noktasındaki bellek erişim işlemini tekrar sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için gibi mekanizmaları kullanın [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md) içinde tanımlanan [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```
void _ReadBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_ReadBarrier` İç kaldırabilir veya arama noktasındaki bellek erişim işlemini yeniden sıralama derleyici iyileştirmelerini sınırlar.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)