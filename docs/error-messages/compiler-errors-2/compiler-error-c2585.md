---
title: "Derleyici Hatası C2585 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2585
dev_langs: C++
helpviewer_keywords: C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb0720c7fa9cde9a735c4353bb6bf1d8714ff0fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2585"></a>Derleyici Hatası C2585
'type ' açık dönüştürme belirsiz  
  
 Tür dönüşümü birden fazla sonuç üretebilir.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Birden çok devralmayı göre bir sınıf veya yapı türü dönüştürme. Aynı temel sınıfı türü birden çok kez devralır, dönüştürme işlevi veya işleci kapsam çözümü kullanmanız gerekir (`::`) Dönüştürmedeki devralınan sınıfların belirtmek için.  
  
2.  Bir dönüşüm işleci ve bir oluşturucu aynı dönüştürme yapma tanımlanmadı.