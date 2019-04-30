---
title: Kural Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: cd82dc5b0693e563fd3d75a0215265089ff57913
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342886"
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

[Yolları kurallarda Ara](search-paths-in-rules.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım Kuralları](inference-rules.md)
