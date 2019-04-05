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
ms.openlocfilehash: 20c583b874c2bdb56affc6a90c8464b82c4824f0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040841"
---
# <a name="inbyte"></a>__inbyte

**Microsoft'a Özgü**

Oluşturur `in` yönerge tarafından belirtilen bağlantı noktası okuma bayt döndüren `Port`.

## <a name="syntax"></a>Sözdizimi

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı Noktası*<br/>
[in] Okunacak bağlantı noktası.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen bağlantı noktasından bayt okuyun.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)