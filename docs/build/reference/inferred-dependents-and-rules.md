---
description: 'Daha fazla bilgi edinin: çıkartılan bağımlılıklar ve kurallar'
title: Çıkarsanan Bağımlılıklar ve Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 9f4c1d14d18c9c693a7bd71f9207ff36aede8e22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191283"
---
# <a name="inferred-dependents-and-rules"></a>Çıkarsanan Bağımlılıklar ve Kurallar

Geçerli bir çıkarım kuralı varsa NMAKE, bir hedef için gösterilen bir bağımlı olduğunu varsayar. Bir kural şu durumlarda geçerlidir:

- *toext* , hedefin uzantısıyla eşleşiyor.

- *fromext* , hedefin temel adına sahip olan ve geçerli veya belirtilen dizinde bulunan bir dosyanın uzantısıyla eşleşir.

- *fromext* içinde [. SON ekler](dot-directives.md); eşleşen kuralda başka bir *fromext* daha yüksektir **. SONEK** önceliği.

- Açık bağımlı, daha yüksek bir değere sahip değildir **. SONEK** önceliği.

Gösterilen bağımlılıklar beklenmedik yan etkilere neden olabilir. Hedefin açıklama bloğu komutlar içeriyorsa, NMAKE kuraldaki komutlar yerine bu komutları yürütür.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım kuralları](inference-rules.md)
