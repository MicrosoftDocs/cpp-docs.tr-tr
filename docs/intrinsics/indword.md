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
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029336"
---
# <a name="indword"></a>__indword

**Microsoft'a özgü**

Belirtilen bağlantı noktası kullanarak verilerin bir çift sözcük okur `in` yönergesi.

## <a name="syntax"></a>Sözdizimi

```
unsigned long __indword(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)