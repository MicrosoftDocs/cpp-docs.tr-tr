---
title: "İfade değerlendirici hatası CXX0019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0019
dev_langs: C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67fbd43280ad6ffcecdf0532819cd80a0d44b479
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0019"></a>İfade Değerlendirici Hatası CXX0019
bozuk tür belirtimi  
  
 C ifade değerlendiricisi yazıldığı şekilde cast türü gerçekleştiremezsiniz.  
  
 Bu hata için CAN0019 aynıdır.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Belirtilen türü bilinmiyor.  
  
2.  İşaretçi türlerinin çok fazla düzeyleri vardı. Örneğin, atama türü  
  
    ```  
    (char **)h_message  
    ```  
  
     C ifade değerlendiricisi tarafından değerlendirilemez.