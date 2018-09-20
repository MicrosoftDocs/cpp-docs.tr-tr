---
title: __readmsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readmsr
dev_langs:
- C++
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d21d33d1e90d7c4aac9ea833d0c5bd80f5172312
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416610"
---
# <a name="readmsr"></a>__readmsr

**Microsoft'a özgü**

Oluşturur `rdmsr` tarafından belirtilen modele özgü yazmacını okuyarak yönerge `register` ve değerini döndürür.

## <a name="syntax"></a>Sözdizimi

```
__int64 __readmsr( 
   int register 
);
```

#### <a name="parameters"></a>Parametreler

*Kaydolun*<br/>
[in] Okuma modeli belirli kaydetme.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen kayıt değeri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

Daha fazla bilgi için AMD belgelerine bakın.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)