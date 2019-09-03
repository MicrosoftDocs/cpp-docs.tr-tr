---
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: c8df13c15b5cd8a51b77d65ad930a1852809ee30
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219241"
---
# <a name="__writecr8"></a>__writecr8

**Microsoft 'a özgü**

Değeri `Data` CR8 kaydına yazar.

## <a name="syntax"></a>Sözdizimi

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parametreler

*Verileri*\
'ndaki CR8 kaydına yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writecr8`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`__writecr8` İç öğe yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
