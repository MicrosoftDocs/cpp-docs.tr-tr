---
description: 'Hakkında daha fazla bilgi edinin: _ReadWriteBarrier'
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: ff537d4f3b117b52ba567bf0d130e51d0062965f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294129"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Microsoft'a Özgü**

Çağrı noktasındaki bellek erişimlerini yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
> `_ReadBarrier`, `_WriteBarrier` , Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makro kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için, [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)'nda tanımlanan [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std:: \<T> atomik](../standard-library/atomic.md)gibi mekanizmalar kullanın. Donanım erişimi için, [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğini [geçici](../cpp/volatile-cpp.md) anahtar sözcüğüyle birlikte kullanın.

## <a name="syntax"></a>Syntax

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_ReadWriteBarrier`İç, çağrı noktasındaki bellek erişimlerini kaldırabilen veya yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_WriteBarrier](../intrinsics/writebarrier.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
