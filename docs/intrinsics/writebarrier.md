---
title: _WriteBarrier | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _WriteBarrier
dev_langs:
- C++
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0004a48a73ee0635f3d71b8b2ceee1ef90993c7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436578"
---
# <a name="writebarrier"></a>_WriteBarrier

**Microsoft'a özgü**

Arama noktasındaki bellek erişim işlemini tekrar sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier`, Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makrosu kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için gibi mekanizmaları kullanın [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std::atomic\<T >](../standard-library/atomic.md), içinde tanımlandığı [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Donanım erişimi için kullandığınız [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ile birlikte [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.

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

## <a name="see-also"></a>Ayrıca Bkz.

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)