---
title: Çıkarsanan bağımlılıklar ve kurallar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13ae7784ff40b39642ce26fd062a1aab80f2d4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707557"
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