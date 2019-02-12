---
title: İfade Değerlendirme (C)
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
ms.openlocfilehash: 37affedc0bcf3fb1423898ecf2c570794d9625c0
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151097"
---
# <a name="expression-evaluation-c"></a>İfade Değerlendirme (C)

Atama ile ilgili ifadelerin, birli artışın, birli azalışın veya bir işlev çağırmanın, değerlendirmelerinde arızi sonuçları olabilir (yan etkiler). Bir "sıra noktasına" ulaşıldığında, sıra noktasını takip eden herhangi bir şey üzerinde değerlendirme başlamadan önce tüm yan etkileri de dahil olmak üzere sıra noktasından önceki her şeyin, değerlendirmesi sağlanır.

"Yan etkiler" bir ifadenin değerlendirilmesinin sebep olduğu değişikliklerdir. Yan etkiler, bir değişkenli değer bir ifade değerlendirmesi tarafından değiştirildiği herhangi bir zamanda olur. Tüm atama işlemlerinin yan etkileri vardır. Dışarıdan görünür bir öğenin değerini işaretçi üzerinden dolaylı atama ile veya doğrudan atama ile değiştirirseniz, işlev çağrılarının da yan etkileri olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)
