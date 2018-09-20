---
title: __outdwordstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outdwordstring
dev_langs:
- C++
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f81b423838d2daa9915dc5330d23e4ef69273bc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395069"
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