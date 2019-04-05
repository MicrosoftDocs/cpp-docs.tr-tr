---
title: __indword
ms.date: 11/04/2016
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: 063ebd92682f8011bc6b60eee14c3443bc04c333
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029336"
---
# <a name="indword"></a>__indword

**Microsoft'a Özgü**

Belirtilen bağlantı noktası kullanarak verilerin bir çift sözcük okur `in` yönergesi.

## <a name="syntax"></a>Sözdizimi

```
unsigned long __indword(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı Noktası*<br/>
[in] Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş Değeri

Word bağlantı noktasından okuyun.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__indword`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)