---
description: 'Hakkında daha fazla bilgi edinin: __faststorefence'
title: __faststorefence
ms.date: 09/02/2019
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: f12d16232e034c562f564d851da08c62cb59c34f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337026"
---
# <a name="__faststorefence"></a>__faststorefence

**Microsoft'a Özgü**

Hem yük hem de depolama belleği başvuruları dahil olmak üzere, önceki tüm bellek başvurularının, sonraki bir bellek başvurusundan önce küresel olarak görünür olmasını güvence altına alır.

## <a name="syntax"></a>Syntax

```C
void __faststorefence();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__faststorefence`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

, Yürütme devam etmeden önce, iç, genel olarak görünür olmadan önce verilen yük ve mağaza işlemlerini garanti eden bir tam bellek engeli yönerge dizisi oluşturur. Efekt, `_mm_mfence` Tüm x64 platformlarındaki iç öğe ile karşılaştırılabilir ancak daha hızlıdır.

AMD64 platformunda Bu yordam, yönergeden daha hızlı bir depolama dilimi olan bir yönerge oluşturur `sfence` . Zaman açısından kritik kod için, yalnızca AMD64 platformlarında bu iç sürümü kullanın `_mm_sfence` . Intel x64 platformlarında, `_mm_sfence` yönerge daha hızlıdır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
