---
description: 'Hakkında daha fazla bilgi edinin: __outwordstring'
title: __outwordstring
ms.date: 09/02/2019
f1_keywords:
- __outwordstring
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
ms.openlocfilehash: c0dba174776c7606a0f9ed11ac172331a6a8f350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257543"
---
# <a name="__outwordstring"></a>__outwordstring

**Microsoft'a Özgü**

`rep outsw` *Bağlantı noktası* tarafından belirtilen g/ç bağlantı noktasını *arabelleğe* alarak başlayan *sayı* sözcüklerini gönderen yönergeyi üretir.

## <a name="syntax"></a>Sözdizimi

```C
void __outwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Arabelleğin*\
'ndaki Belirtilen bağlantı noktasını göndermek için veri işaretçisi.

*Biriktirme*\
'ndaki Gönderilen sözcüklerin sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outwordstring`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
