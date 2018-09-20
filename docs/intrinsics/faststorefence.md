---
title: __faststorefence | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5047dbb2023272ab03cc7d49f877f0fcc38a7b76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402193"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)