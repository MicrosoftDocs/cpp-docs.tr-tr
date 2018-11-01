---
title: İfade Değerlendirme (C)
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
ms.openlocfilehash: 58478830d901836fc82ee02412c86a776a2c1998
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522362"
---
# <a name="expression-evaluation-c"></a>İfade Değerlendirme (C)

Atama ile ilgili ifadelerin, birli artışın, birli azalışın veya bir işlev çağırmanın, değerlendirmelerinde arızi sonuçları olabilir (yan etkiler). Bir "sıra noktasına" ulaşıldığında, sıra noktasını takip eden herhangi bir şey üzerinde değerlendirme başlamadan önce tüm yan etkileri de dahil olmak üzere sıra noktasından önceki her şeyin, değerlendirmesi sağlanır.

"Yan etkiler" bir ifadenin değerlendirilmesinin sebep olduğu değişikliklerdir. Yan etkiler, bir değişkenli değer bir ifade değerlendirmesi tarafından değiştirildiği herhangi bir zamanda olur. Tüm atama işlemlerinin yan etkileri vardır. Dışarıdan görünür bir öğenin değerini işaretçi üzerinden dolaylı atama ile veya doğrudan atama ile değiştirirseniz, işlev çağrılarının da yan etkileri olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)