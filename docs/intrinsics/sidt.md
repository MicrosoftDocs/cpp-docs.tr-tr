---
description: 'Hakkında daha fazla bilgi edinin: __sidt'
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 075351bc10981dd8453381e9ce9393a046dfd884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306969"
---
# <a name="__sidt"></a>__sidt

**Microsoft'a Özgü**

Kesme tanımlayıcısı tablo yazmacın (ıDTR) değerini belirtilen bellek konumunda depolar.

## <a name="syntax"></a>Sözdizimi

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
'ndaki IDTR 'ın depolandığı bellek konumuna yönelik bir işaretçi.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__sidt`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`__sidt`İşlev, `SIDT` makine yönergesine eşdeğerdir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde "Intel mimarisi yazılım geliştiricisi el kitabı, toplu 2: yönerge kümesi başvurusu" belgesinde arama yapın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
