---
title: __inwordstring
ms.date: 11/04/2016
f1_keywords:
- __inwordstring
- __inwordstring_cpp
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
ms.openlocfilehash: 52c36754e1eea56b84eeb494e82e37a5b043246e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030225"
---
# <a name="inwordstring"></a>__inwordstring

**Microsoft'a Özgü**

Belirtilen bağlantı noktası kullanarak verileri okuyan `rep insw` yönergesi.

## <a name="syntax"></a>Sözdizimi

```
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı Noktası*<br/>
[in] Okunacak bağlantı noktası.

*Arabellek*<br/>
[out] Bağlantı noktasından okunan veriler burada yazılır.

*Sayı*<br/>
[in] Veri okumak için sözcük sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__inwordstring`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)