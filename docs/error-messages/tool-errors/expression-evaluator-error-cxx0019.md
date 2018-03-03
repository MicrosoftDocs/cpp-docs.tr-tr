---
title: "İfade değerlendirici hatası CXX0019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c62391bb770a49810a87c52b2f75d5a0d4426fbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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