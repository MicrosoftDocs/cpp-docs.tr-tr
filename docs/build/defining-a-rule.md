---
title: Kural tanımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a5cb7a0285f7abf8bcf476141451eae1b10f85
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705581"
---
# <a name="defining-a-rule"></a>Kural Tanımlama

*Fromext* bağımlı bir dosyanın uzantısını temsil eder ve *toext* hedef dosya uzantısını temsil eder.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Açıklamalar

Uzantılar büyük/küçük harfe duyarlı değildir. Makrolar temsil etmek için çağrılacak *fromext* ve *toext*; ön işleme sırasında makroları genişletilir. Önceki nokta (.) *fromext* satırın başında yer almalıdır. İki nokta üst üste (:) sıfır veya daha fazla boşluk veya sekme gelmelidir. Yalnızca boşluk veya sekme, komutu belirtmek için noktalı virgül (;), yorum belirtmek için bir sayı işaretiyle (#) veya yeni satır karakteri tarafından izlenebilir. Diğer boşluk izin verilir. Açıklama blokları olduğu gibi komutları belirtilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Yolları kurallarda Ara](../build/search-paths-in-rules.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)