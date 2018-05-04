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
ms.openlocfilehash: 9c250cba9e26d82ba129a842b61006783d13f6e3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="expression-evaluation-c"></a>İfade Değerlendirme (C)
Atama ile ilgili ifadelerin, birli artışın, birli azalışın veya bir işlev çağırmanın, değerlendirmelerinde arızi sonuçları olabilir (yan etkiler). Bir "sıra noktasına" ulaşıldığında, sıra noktasını takip eden herhangi bir şey üzerinde değerlendirme başlamadan önce tüm yan etkileri de dahil olmak üzere sıra noktasından önceki her şeyin, değerlendirmesi sağlanır.  
  
 "Yan etkiler" bir ifadenin değerlendirilmesinin sebep olduğu değişikliklerdir. Yan etkiler, bir değişkenli değer bir ifade değerlendirmesi tarafından değiştirildiği herhangi bir zamanda olur. Tüm atama işlemlerinin yan etkileri vardır. Dışarıdan görünür bir öğenin değerini işaretçi üzerinden dolaylı atama ile veya doğrudan atama ile değiştirirseniz, işlev çağrılarının da yan etkileri olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)