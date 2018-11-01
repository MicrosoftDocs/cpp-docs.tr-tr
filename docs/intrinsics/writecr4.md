---
title: __writecr4
ms.date: 11/04/2016
f1_keywords:
- _writecr4
helpviewer_keywords:
- _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
ms.openlocfilehash: debfaf0bb591cde43506d18342a8f24d3883b576
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513834"
---
# <a name="writecr4"></a>__writecr4

**Microsoft'a özgü**

Değeri Yazar `Data` CR4 kaydı.

## <a name="syntax"></a>Sözdizimi

```
void writecr4( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parametreler

*Veri*<br/>
[in] CR4 kasaya yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writecr4`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)