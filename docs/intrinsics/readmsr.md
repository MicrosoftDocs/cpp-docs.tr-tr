---
title: __readmsr
ms.date: 11/04/2016
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 891ca43af4a81b63de39d367ea418e43811f78d0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326413"
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