---
title: COMM | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df6c729ab130a7ff38d7f7cf83224e7425e7dba
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463029"
---
# <a name="comm"></a>COMM

Belirtilen özniteliklerle müşterek bir değişken oluşturur *tanımı*.

## <a name="syntax"></a>Sözdizimi

> **COMM** *tanımı* [, *tanımı*]...

## <a name="remarks"></a>Açıklamalar

Müşterek değişkenleri bağlayıcı tarafından ayrılmış ve başlatılamaz. Başka bir deyişle, konumu ya da böyle değişkenlerin sırası bağımlı olamaz.

Her *tanımı* aşağıdaki biçime sahiptir:

[*langtype*] [**NEAR** &#124; **uzak**] _etiket_**:**_türü_[**:**_sayısı_]

İsteğe bağlı *langtype* izleyen ad için adlandırma kurallarını ayarlar. Tarafından belirtilen herhangi bir dil geçersiz kılmaları **. MODEL** yönergesi. İsteğe bağlı **NEAR** veya **uzak** geçerli bellek modeli geçersiz. *Etiket* değişkenin adıdır. *Türü* hiçbir tür belirteci olabilir ([bayt](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı. İsteğe bağlı *sayısı* bildirilen veri nesnesinde; öğelerin sayısını belirler varsayılan biridir.

## <a name="example"></a>Örnek

Bu örnek, 512 BAYTLIK öğeleri dizisi oluşturur:

```masm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
