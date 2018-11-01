---
title: Çıkarsanan Bağımlılıklar ve Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 6d2f439a0e936b06012045c62d55b6ad76e5817d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548908"
---
# <a name="inferred-dependents-and-rules"></a>Çıkarsanan Bağımlılıklar ve Kurallar

Geçerli çıkarım kuralı varsa, bir hedef için gösterilen bir bağımlı NMAKE varsayar. Bir kural uygular:

- *toext* hedefin uzantısı eşleşir.

- *fromext* eşleşen hedef temel ad ve bir dosya uzantısı geçerli ya da belirtilen dizinde bulunmaktadır.

- *fromext* bulunduğu [. SONEKLERİ](../build/dot-directives.md); başka hiçbir *fromext* bir eşleşen kuralı daha yüksek bir sahip **. SONEKLERİ** öncelik.

- Hiçbir açık bağımlı daha yüksek bir sahip **. SONEKLERİ** öncelik.

Çıkarsanan bağımlılıklar beklenmeyen etkilere neden olabilir. Hedefin açıklama bloğu komutları içeriyorsa, NMAKE kuralda komutlar yerine bu komutları yürütür.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)