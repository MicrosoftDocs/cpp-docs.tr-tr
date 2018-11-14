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
ms.openlocfilehash: 059d9344fa329e69666abaca4d73122ab29f8d2a
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326439"
---
# <a name="readpmc"></a>__readpmc

**Microsoft'a özgü**

Oluşturur `rdpmc` performans sayacı tarafından belirtilen izleme okur yönerge `counter`.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __readpmc(
   unsigned long counter
);
```

#### <a name="parameters"></a>Parametreler

*Sayaç*<br/>
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)