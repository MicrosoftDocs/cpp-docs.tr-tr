---
title: "Birincil ifadelerdeki tanımlayıcılar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e507c2b7c05f9ea818f55b10d222592fe0172cc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="identifiers-in-primary-expressions"></a>Birincil İfadelerdeki Tanımlayıcılar
Tanımlayıcıları integral olabilir **float**, `enum`, `struct`, **UNION**, dizi, işaretçi veya işlev türü. (Bu durumda bu, l-değeri'dir) bir nesne belirleme veya bir işlev (Bu durumda bu, bir işlev Belirleyicisi'dir) olarak bildirilmiş bir birincil ifadesi sağlanan bir tanımlayıcıdır. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) l-değeri tanımının için.  
  
 Böylece bir dizi tanımlayıcı form sol işleneni bir atama işleminin olamaz ve bu nedenle değiştirilebilir l-değeri değil, bir dizi tanımlayıcı tarafından gösterilen işaretçi değeri bir değişken değil.  
  
 Bir işlevi olarak bildirilen bir tanımlayıcı değeri işlevi adresidir bir işaretçi temsil eder. Belirtilen türde bir değer döndüren bir işlev işaretçisi giderir. Bu nedenle, işlev tanımlayıcıları l değerleri atama işlemlerinde olamaz. Daha fazla bilgi için bkz: [tanımlayıcıları](../c-language/c-identifiers.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Birincil İfadeler](../c-language/c-primary-expressions.md)