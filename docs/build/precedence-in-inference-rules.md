---
title: Çıkarsama Kurallarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 30dee54c99115c076f7662bafb8aa22d97f234fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548739"
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik

NMAKE çıkarım kuralı birden çok kez tanımlanmış, en yüksek öncelikli tanımı kullanır. Aşağıdaki liste, en yüksek öncelikten en düşüğe sırasını gösterir:

1. Derleme görevleri dosyasında tanımlanan bir çıkarma kuralı; sonraki tanımları önceliğe sahip olur.

1. Tools.ini içinde tanımlanan bir çıkarma kuralı; sonraki tanımları önceliğe sahip olur.

1. Bir önceden tanımlanmış çıkarım kuralı.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)