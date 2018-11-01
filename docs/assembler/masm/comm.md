---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 342c8acd95fd45de1a21dc298325de9a7b40b717
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434807"
---
# <a name="comm"></a>COMM

Belirtilen özniteliklerle müşterek bir değişken oluşturur *tanımı*.

## <a name="syntax"></a>Sözdizimi

> **COMM** *tanımı* [, *tanımı*]...

## <a name="remarks"></a>Açıklamalar

Müşterek değişkenleri bağlayıcı tarafından ayrılır ve başlatılamaz. Başka bir deyişle, konum veya bu değişkenleri dizisini bağımlı olamaz.

Her *tanımı* aşağıdaki biçime sahiptir:

[*langtype*] [**yakın** &#124; **uzak**] _etiket_**:**_türü_[**:**_sayısı_]

İsteğe bağlı *langtype* izleyen ad için adlandırma kuralları ayarlar. Tarafından belirtilen herhangi bir dilde onu geçersiz kılar **. MODEL** yönergesi. İsteğe bağlı **yakın** veya **uzak** geçerli bellek modeli geçersiz. *Etiket* değişkenin adıdır. *Türü* herhangi bir tür belirleyiciye olabilir ([bayt](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı. İsteğe bağlı *sayısı* bildirilen veri nesnesi içinde; öğe sayısını belirtir bir varsayılandır.

## <a name="example"></a>Örnek

Bu örnek, bir dizi bir 512 BAYTLIK öğeleri oluşturur:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>
