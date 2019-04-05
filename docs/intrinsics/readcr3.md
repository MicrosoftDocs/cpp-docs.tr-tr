---
title: __readcr3
ms.date: 11/04/2016
f1_keywords:
- __readcr3
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
ms.openlocfilehash: 8b5839d233154b6ddb69d2bbe0b13497c3b66305
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031121"
---
# <a name="readcr3"></a>__readcr3

**Microsoft'a Özgü**

CR3 yazmacını okuyarak ve değerini döndürür.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __readcr3(void);
```

## <a name="return-value"></a>Dönüş Değeri

CR3 kayıttaki değeri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readcr3`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)