---
title: __faststorefence
ms.date: 11/04/2016
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: a0c8027f443a475b03521920e2e036e7ed4eaafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349010"
---
# <a name="faststorefence"></a>__faststorefence

**Microsoft'a özgü**

Her ikisi de dahil olmak üzere her önceki bellek başvuru yüklemek ve bellek başvuruları depolamak garantileri önce herhangi bir sonraki bellek başvurusu genel olarak görünür.

## <a name="syntax"></a>Sözdizimi

```
void __faststorefence();
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__faststorefence`|X64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Garanti yükleyin ve depolama işlemleri bir tam bellek barrier yönergesi bir sıra üretir önce bu iç olan genel olarak yayımlanan yürütmeden önce görünür devam eder. Efekt için karşılaştırılabilir ancak daha hızlı bir şekilde `_mm_mfence` tüm x64 iç platformlar.

AMD64 platformunda, bu yordam daha hızlı bir depolama sınırı olan bir yönerge oluşturur `sfence` yönergesi. Zaman açısından kritik kod için bu iç yerine kullanmak `_mm_sfence` AMD64 platformlarına çağırmasıdır. Intel x64 platformlarda `_mm_sfence` yönergedir daha hızlı.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)