---
title: "Atama dönüşümleri | Microsoft Docs"
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
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94087d5e07765b1052404a4c3e51f37db2a31e3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assignment-conversions"></a>Atama Dönüştürmeleri
Atama işlemlerinde, atanan değerin türü atamayı alan değişkenin türüne dönüştürülür. C, bu bilgi dönüştürme sırasında kaybolsa bile integral ve kayan türler arasında atama ile yapılan dönüştürmelere izin verir. Kullanılan dönüştürme yöntem atamasını ilgili türleri açıklandığı gibi bağlıdır [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) ve aşağıdaki bölümlerdeki:  
  
-   [İmzalı Tam Sayı Türlerinden Dönüştürmeler](../c-language/conversions-from-signed-integral-types.md)  
  
-   [İmzasız Tam Sayı Türlerinden Dönüştürmeler](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Kayan Nokta Türlerinden Dönüşümler](../c-language/conversions-from-floating-point-types.md)  
  
-   [İşaretçi Türlerine ve Türlerinden Dönüşümler](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Diğer Türlerden Dönüştürmeler](../c-language/conversions-from-other-types.md)  
  
 Tür niteleyicileri etkilemez dönüştürme allowability rağmen bir **const** l-değeri atamasını sol tarafta kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür Dönüştürmeleri](../c-language/type-conversions-c.md)