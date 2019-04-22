---
title: _WriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: d2db648c9f41bd4f773f5bf152f31cf990a75c8e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025778"
---
# <a name="writebarrier"></a>_WriteBarrier

**Microsoft'a özgü**

Arama noktasındaki bellek erişim işlemini tekrar sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için gibi mekanizmaları kullanın [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md), içinde tanımlandığı [ C++ StandartKitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```
void _WriteBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_WriteBarrier` İç kaldırabilir veya arama noktasındaki bellek erişim işlemini yeniden sıralama derleyici iyileştirmelerini sınırlar.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)