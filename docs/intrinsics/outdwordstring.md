---
title: __outdwordstring
ms.date: 11/04/2016
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 5579258c813850cdb8f29758bb4bd5d87270467f
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330287"
---
# <a name="outdwordstring"></a>__outdwordstring

**Microsoft'a özgü**

Oluşturur `rep outsd` gönderen yönerge `Count` başlayan doublewords `Buffer` çıkış tarafından belirtilen g/ç bağlantı noktasına `Port`.

## <a name="syntax"></a>Sözdizimi

```
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.

*Arabellek*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek verileri için bir işaretçi.

*Sayısı*<br/>
[in] Gönderilecek doublewords sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__outdwordstring`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)