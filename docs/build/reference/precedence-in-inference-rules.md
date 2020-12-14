---
description: 'Daha fazla bilgi edinin: çıkarım kurallarında öncelik'
title: Çıkarsama Kurallarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: b56d01cce63aaaac92e011630e45bcf43e7fe0b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225914"
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik

Bir çıkarım kuralı tanımlanmazsa, NMAKE en yüksek öncelikli tanımı kullanır. Aşağıdaki listede, en yüksekten en düşüğe öncelik sırası gösterilmektedir:

1. Derleme görevleri dosyasında tanımlanan bir çıkarım kuralı; sonraki tanımlarda öncelik vardır.

1. Tools.ini tanımlanmış bir çıkarım kuralı sonraki tanımlarda öncelik vardır.

1. Önceden tanımlanmış bir çıkarım kuralı.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım kuralları](inference-rules.md)
