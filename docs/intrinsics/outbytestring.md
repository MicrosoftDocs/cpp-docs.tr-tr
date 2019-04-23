---
title: __outbytestring
ms.date: 11/04/2016
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: 41064dda6a1a0b9ad4c15f98c3f3081f08ef8db6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032199"
---
# <a name="outbytestring"></a>__outbytestring

**Microsoft'a özgü**

Oluşturur `rep outsb` gönderen ilk yönerge `Count` verileri baytlık tarafından işaret edilen `Buffer` tarafından belirtilen bağlantı noktasına `Port`.

## <a name="syntax"></a>Sözdizimi

```
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.

*Arabellek*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek veri.

*Sayısı*<br/>
[in] Veri gönderilecek bayt sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)