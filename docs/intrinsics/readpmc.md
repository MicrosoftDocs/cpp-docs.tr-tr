---
title: __readpmc
ms.date: 11/04/2016
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: 848c880e76d6d431ee56a0bb30a33b276837ce76
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029349"
---
# <a name="readpmc"></a>__readpmc

**Microsoft'a Özgü**

Oluşturur `rdpmc` performans sayacı tarafından belirtilen izleme okur yönerge `counter`.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __readpmc(
   unsigned long counter
);
```

#### <a name="parameters"></a>Parametreler

*sayaç*<br/>
[in] Okunacak performans sayacı.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen performans sayacı değeri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readpmc`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)