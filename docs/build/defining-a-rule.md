---
title: Kural Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 0e8356f57b85d503328bb282e2f9f785ac20fa4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431177"
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