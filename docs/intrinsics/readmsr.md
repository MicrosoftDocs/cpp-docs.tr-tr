---
description: 'Hakkında daha fazla bilgi edinin: __readmsr'
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 1a8acae272a450cb4470744e434277576cc8b9c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271921"
---
# <a name="__readmsr"></a>__readmsr

**Microsoft'a Özgü**

`rdmsr`Tarafından belirtilen modele özgü kaydı okuyan **`register`** ve değerini döndüren yönergeyi üretir.

## <a name="syntax"></a>Sözdizimi

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Parametreler

*kaydolunamadı*\
'ndaki Okunacak modele özgü kayıt.

## <a name="return-value"></a>Döndürülen değer

Belirtilen kayıttaki değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca iç öğe olarak kullanılabilir.

Daha fazla bilgi için bkz. AMD belgeleri.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
