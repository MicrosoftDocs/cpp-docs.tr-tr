---
title: Atama dönüşümleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928f80375ecdd33902a0586cf31091d5764ee160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381840"
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