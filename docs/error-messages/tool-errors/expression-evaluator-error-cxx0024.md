---
title: İfade değerlendirici hatası CXX0024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a07297ddabf269b003a1f14d967d1187fea96d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024
işlemi l-değeri gerekiyor  
  
 L-değeri gerektiren bir işlem için bir l-değeri değerlendirmez bir ifade belirtildi.  
  
 (Bu nedenle Atama ifadesinin sol tarafında görünür olduğundan denir) bir l-değeri bir bellek konumuna başvurduğu bir ifadedir.  
  
 Örneğin, `buffer[count]` belirli bellek konumuna işaret geçerli l-değeri olmasıdır. Mantıksal karşılaştırma `zed != 0` bunu TRUE veya FALSE, bir bellek adresi değil olarak değerlendirildiği bir l-değeri geçerli değil.  
  
 Bu hata için CAN0024 aynıdır.