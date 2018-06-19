---
title: Ek işleçlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44259ef77e5f09a1723064683c6900e425eb35c0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385926"
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