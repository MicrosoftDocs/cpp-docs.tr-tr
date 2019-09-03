---
title: __faststorefence
ms.date: 09/02/2019
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: d11a20666612fe1bca22f5d46b93e898dae375f6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222182"
---
# <a name="__faststorefence"></a>__faststorefence

**Microsoft 'a özgü**

Hem yük hem de depolama belleği başvuruları dahil olmak üzere, önceki tüm bellek başvurularının, sonraki bir bellek başvurusundan önce küresel olarak görünür olmasını güvence altına alır.

## <a name="syntax"></a>Sözdizimi

```C
void __faststorefence();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__faststorefence`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

, Yürütme devam etmeden önce, iç, genel olarak görünür olmadan önce verilen yük ve mağaza işlemlerini garanti eden bir tam bellek engeli yönerge dizisi oluşturur. Efekt, tüm x64 platformlarındaki `_mm_mfence` iç öğe ile karşılaştırılabilir ancak daha hızlıdır.

AMD64 platformunda Bu yordam, `sfence` yönergeden daha hızlı bir depolama dilimi olan bir yönerge oluşturur. Zaman açısından kritik kod için, yalnızca AMD64 platformlarında bu iç `_mm_sfence` sürümü kullanın. Intel x64 platformlarında, `_mm_sfence` yönerge daha hızlıdır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
