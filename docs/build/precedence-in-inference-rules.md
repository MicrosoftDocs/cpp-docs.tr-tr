---
title: Çıkarsama kurallarında öncelik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4f2e7ff55e935b7e425b552ba85f47f134c6b80
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725237"
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik

NMAKE çıkarım kuralı birden çok kez tanımlanmış, en yüksek öncelikli tanımı kullanır. Aşağıdaki liste, en yüksek öncelikten en düşüğe sırasını gösterir:

1. Derleme görevleri dosyasında tanımlanan bir çıkarma kuralı; sonraki tanımları önceliğe sahip olur.

1. Tools.ini içinde tanımlanan bir çıkarma kuralı; sonraki tanımları önceliğe sahip olur.

1. Bir önceden tanımlanmış çıkarım kuralı.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)