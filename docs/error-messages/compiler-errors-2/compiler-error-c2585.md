---
title: "Derleyici Hatası C2585 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>Derleyici Hatası C2585
'type ' açık dönüştürme belirsiz  
  
 Tür dönüşümü birden fazla sonuç üretebilir.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Birden çok devralmayı göre bir sınıf veya yapı türü dönüştürme. Aynı temel sınıfı türü birden çok kez devralır, dönüştürme işlevi veya işleci kapsam çözümü kullanmanız gerekir (`::`) Dönüştürmedeki devralınan sınıfların belirtmek için.  
  
2.  Bir dönüşüm işleci ve bir oluşturucu aynı dönüştürme yapma tanımlanmadı.