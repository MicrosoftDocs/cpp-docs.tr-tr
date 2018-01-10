---
title: "İfade Evaluation (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9984444bd7de3144cb1e81ddb527c68531a9d7d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluation-c"></a>İfade Değerlendirme (C)
Atama ile ilgili ifadelerin, birli artışın, birli azalışın veya bir işlev çağırmanın, değerlendirmelerinde arızi sonuçları olabilir (yan etkiler). Bir "sıra noktasına" ulaşıldığında, sıra noktasını takip eden herhangi bir şey üzerinde değerlendirme başlamadan önce tüm yan etkileri de dahil olmak üzere sıra noktasından önceki her şeyin, değerlendirmesi sağlanır.  
  
 "Yan etkiler" bir ifadenin değerlendirilmesinin sebep olduğu değişikliklerdir. Yan etkiler, bir değişkenli değer bir ifade değerlendirmesi tarafından değiştirildiği herhangi bir zamanda olur. Tüm atama işlemlerinin yan etkileri vardır. Dışarıdan görünür bir öğenin değerini işaretçi üzerinden dolaylı atama ile veya doğrudan atama ile değiştirirseniz, işlev çağrılarının da yan etkileri olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)