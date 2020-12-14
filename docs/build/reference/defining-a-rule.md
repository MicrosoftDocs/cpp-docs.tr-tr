---
description: 'Daha fazla bilgi edinin: kural tanımlama'
title: Kural Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 89a5db90162ede02743aa469ac4f9e3d75c5e147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201683"
---
# <a name="defining-a-rule"></a>Kural Tanımlama

*Fromext* , bağımlı bir dosyanın uzantısını temsil eder ve *toext* , bir hedef dosyanın uzantısını temsil eder.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Açıklamalar

Uzantılar büyük/küçük harfe duyarlı değildir. Makrolar, *fromext* ve *toext*'yi temsil edecek şekilde çağrılabilir; makrolar ön işleme sırasında genişletilir. Önceki *fromext* 'nin nokta (.) satırının başında görünmelidir. İki nokta (:) önünde sıfır veya daha fazla boşluk veya sekme bulunur. Bu, yalnızca boşluk veya sekme ile bir noktalı virgül (;) bir komut, bir açıklama belirtmek için bir sayı işareti (#) veya yeni satır karakteri. Başka boşluğa izin verilmez. Komutlar açıklama bloklarıyla olarak belirtilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Yolları kurallarda ara](search-paths-in-rules.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım kuralları](inference-rules.md)
