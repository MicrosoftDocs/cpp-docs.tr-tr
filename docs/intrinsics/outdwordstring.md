---
description: 'Hakkında daha fazla bilgi edinin: __outdwordstring'
title: __outdwordstring
ms.date: 09/02/2019
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 3fbba7dd128666b591305326695e656befd9cada
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180402"
---
# <a name="__outdwordstring"></a>__outdwordstring

**Microsoft'a Özgü**

`rep outsd` `Count` `Buffer` Tarafından belirtilen g/ç bağlantı noktasından başlayarak doublewords gönderen yönergeyi üretir `Port` .

## <a name="syntax"></a>Sözdizimi

```C
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Arabelleğin*\
'ndaki Belirtilen bağlantı noktasını göndermek için veri işaretçisi.

*Biriktirme*\
'ndaki Gönderilen doublewords sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outdwordstring`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
