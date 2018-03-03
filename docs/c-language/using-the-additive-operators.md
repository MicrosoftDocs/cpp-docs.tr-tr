---
title: "Ek işleçlerini kullanma | Microsoft Docs"
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
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94e2a63412e4fecd5f358659cc4bf02f90df57ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-additive-operators"></a>Ek İşleçlerini Kullanma
Aşağıdaki örneklerde, toplama ve çıkarma işleçleri gösterilmekte ve bu bildirimler kullanılmaktadır:  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Bu deyimler eşdeğerdir:  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 Değeri `i` uzunluğuna çarpılır bir **float** ve eklenen `&x[4]`. Sonuçta elde edilen işaretçi değeri, `x[8]` adresidir.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 Bu örnekte, üçüncü `x` öğesinin (`x[i-2]` tarafından verilmiştir) adresi, beşinci `x` öğesinin (`x[i]` tarafından verilmiştir) adresinden çıkarılır. Fark uzunluğuna bölünmüş bir **float**; tamsayı değeri 2 sonucudur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Ek İşleçleri](../c-language/c-additive-operators.md)