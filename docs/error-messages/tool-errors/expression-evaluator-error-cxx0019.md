---
title: İfade değerlendirici hatası CXX0019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52e1679374e105ab06ce245ba68cfe92706689e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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