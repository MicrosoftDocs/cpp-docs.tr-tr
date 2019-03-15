---
title: Çıkarsanan Bağımlılıklar ve Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: b9c3055db0cc173999e1737986166eb334dcf96c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823715"
---
# <a name="inferred-dependents-and-rules"></a>Çıkarsanan Bağımlılıklar ve Kurallar

Geçerli çıkarım kuralı varsa, bir hedef için gösterilen bir bağımlı NMAKE varsayar. Bir kural uygular:

- *toext* hedefin uzantısı eşleşir.

- *fromext* eşleşen hedef temel ad ve bir dosya uzantısı geçerli ya da belirtilen dizinde bulunmaktadır.

- *fromext* bulunduğu [. SONEKLERİ](dot-directives.md); başka hiçbir *fromext* bir eşleşen kuralı daha yüksek bir sahip **. SONEKLERİ** öncelik.

- Hiçbir açık bağımlı daha yüksek bir sahip **. SONEKLERİ** öncelik.

Çıkarsanan bağımlılıklar beklenmeyen etkilere neden olabilir. Hedefin açıklama bloğu komutları içeriyorsa, NMAKE kuralda komutlar yerine bu komutları yürütür.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım Kuralları](inference-rules.md)
