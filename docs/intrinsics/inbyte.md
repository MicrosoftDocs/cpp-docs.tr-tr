---
title: __inbyte
ms.date: 11/04/2016
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 63d4e9229eb7c5058587975d0ea04696786a9c73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562155"
---
# <a name="inbyte"></a>__inbyte

**Microsoft'a özgü**

Oluşturur `in` yönerge tarafından belirtilen bağlantı noktası okuma bayt döndüren `Port`.

## <a name="syntax"></a>Sözdizimi

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
[in] Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen bağlantı noktasından bayt okuyun.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)