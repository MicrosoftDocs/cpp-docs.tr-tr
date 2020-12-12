---
description: 'Hakkında daha fazla bilgi edinin: _ReadBarrier'
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 94ade7c8f602cf279ac75a5f0a56387c344d0fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257504"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Microsoft'a Özgü**

Bellek erişim işlemlerini çağrı noktası boyunca yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

> [!CAUTION]
> `_ReadBarrier`, `_WriteBarrier` , Ve `_ReadWriteBarrier` derleyici iç bilgileri ve `MemoryBarrier` makro kullanım dışıdır ve kullanılmamalıdır. İş parçacıkları arası iletişim için, [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)'nda tanımlanan [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) ve [std:: \<T> atomik](../standard-library/atomic.md) gibi mekanizmalar kullanın. Donanım erişimi için, [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğini [geçici](../cpp/volatile-cpp.md) anahtar sözcüğüyle birlikte kullanın.

## <a name="syntax"></a>Syntax

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_ReadBarrier`İç, çağrı noktasındaki bellek erişimi işlemlerini kaldırabilen veya yeniden sıralayabileceğiniz derleyici iyileştirmelerini sınırlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
