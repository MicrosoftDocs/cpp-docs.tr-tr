---
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: d6b685da0e02373307a3149c5b7b28213f37ad40
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222330"
---
# <a name="__sidt"></a>__sidt

**Microsoft 'a özgü**

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

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İşlev, `SIDT` makine yönergesine eşdeğerdir. `__sidt` Daha fazla bilgi için belgeyi arayın, "Intel mimarisi yazılım geliştiricisi El Ile, birim 2: Yönerge kümesi başvurusu, " [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
