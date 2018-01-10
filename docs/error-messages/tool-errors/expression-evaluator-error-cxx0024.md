---
title: "İfade değerlendirici hatası CXX0024 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0024
dev_langs: C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96bd943719afb0d974a5c4386742bea24396fd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024
işlemi l-değeri gerekiyor  
  
 L-değeri gerektiren bir işlem için bir l-değeri değerlendirmez bir ifade belirtildi.  
  
 (Bu nedenle Atama ifadesinin sol tarafında görünür olduğundan denir) bir l-değeri bir bellek konumuna başvurduğu bir ifadedir.  
  
 Örneğin, `buffer[count]` belirli bellek konumuna işaret geçerli l-değeri olmasıdır. Mantıksal karşılaştırma `zed != 0` bunu TRUE veya FALSE, bir bellek adresi değil olarak değerlendirildiği bir l-değeri geçerli değil.  
  
 Bu hata için CAN0024 aynıdır.