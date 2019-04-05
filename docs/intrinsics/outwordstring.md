---
title: __outwordstring
ms.date: 11/04/2016
f1_keywords:
- __outwordstring
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
ms.openlocfilehash: d7141dd7f9f1f81e905952959e392a23d141f4e4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030374"
---
# <a name="outwordstring"></a>__outwordstring

**Microsoft'a Özgü**

Oluşturur `rep outsw` gönderen yönerge `Count` başlayan sözcükleri `Buffer` çıkış tarafından belirtilen g/ç bağlantı noktasına `Port`.

## <a name="syntax"></a>Sözdizimi

```
void __outwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı Noktası*<br/>
[in] Veri göndermek için bağlantı noktası.

*Arabellek*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek verileri için bir işaretçi.

*Sayı*<br/>
[in] Gönderilecek sözcük sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__outwordstring`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)