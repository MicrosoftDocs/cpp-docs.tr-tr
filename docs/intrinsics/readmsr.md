---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 4398b9d42369e3a914dbec1ed2d14cafecf58483
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222345"
---
# <a name="__readmsr"></a>__readmsr

**Microsoft 'a özgü**

`rdmsr` Tarafından`register` belirtilen modele özgü kaydı okuyan ve değerini döndüren yönergeyi üretir.

## <a name="syntax"></a>Sözdizimi

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Parametreler

*kaydolunamadı*\
'ndaki Okunacak modele özgü kayıt.

## <a name="return-value"></a>Dönüş değeri

Belirtilen kayıttaki değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca iç öğe olarak kullanılabilir.

Daha fazla bilgi için bkz. AMD belgeleri.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
