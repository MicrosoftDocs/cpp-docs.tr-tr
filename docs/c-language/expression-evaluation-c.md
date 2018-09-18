---
title: İfade Evaluation (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f97b28067d6257ea14255d3e049adcae99f73ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060947"
---
# <a name="expression-evaluation-c"></a>İfade Değerlendirme (C)

Atama ile ilgili ifadelerin, birli artışın, birli azalışın veya bir işlev çağırmanın, değerlendirmelerinde arızi sonuçları olabilir (yan etkiler). Bir "sıra noktasına" ulaşıldığında, sıra noktasını takip eden herhangi bir şey üzerinde değerlendirme başlamadan önce tüm yan etkileri de dahil olmak üzere sıra noktasından önceki her şeyin, değerlendirmesi sağlanır.

"Yan etkiler" bir ifadenin değerlendirilmesinin sebep olduğu değişikliklerdir. Yan etkiler, bir değişkenli değer bir ifade değerlendirmesi tarafından değiştirildiği herhangi bir zamanda olur. Tüm atama işlemlerinin yan etkileri vardır. Dışarıdan görünür bir öğenin değerini işaretçi üzerinden dolaylı atama ile veya doğrudan atama ile değiştirirseniz, işlev çağrılarının da yan etkileri olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)