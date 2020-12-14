---
description: 'Hakkında daha fazla bilgi edinin: __readpmc'
title: __readpmc
ms.date: 09/02/2019
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: ceff8522d4895f69a47cf429e59d267c671e3a66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294138"
---
# <a name="__readpmc"></a>__readpmc

**Microsoft'a Özgü**

`rdpmc` *Sayaç* tarafından belirtilen performans izleme sayacını okuyan yönergeyi üretir.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __readpmc(
   unsigned long counter
);
```

### <a name="parameters"></a>Parametreler

*sayaç*\
'ndaki Okunacak performans sayacı.

## <a name="return-value"></a>Döndürülen değer

Belirtilen performans sayacının değeri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readpmc`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç öğe yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
