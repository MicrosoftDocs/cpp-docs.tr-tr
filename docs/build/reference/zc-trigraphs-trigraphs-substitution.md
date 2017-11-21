---
title: "-Zc: trigrafları (Trigrafları değiştirme) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56068f6cb630ac12b9c8417940411616cec65c69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigrafları Değiştirme)
Zaman **/ZC: trigraphs** belirtilirse, derleyici, karşılık gelen bir noktalama karakteri kullanarak trigrafı karakter dizisi yerini alır. Trigrafı değiştirmeyi devre dışı bırakmak için şunu belirtin **/Zc:trigraphs-**. Varsayılan olarak, **/ZC: trigraphs** kapalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir trigrafı oluşur iki ardışık soru işaretleri ("??") benzersiz bir üçüncü karakter. Örneğin, derleyici değiştirir "?? = "'#' karakteri kullanarak trigrafı. Bazı noktalama karakterleri için uygun grafik sunumlarını içermeyen bir karakter kümesi kullanan C kaynak dosyalarında trigrafları kullanın.  
  
 C/C++ trigrafları ve trigrafları kullanmayı gösteren bir örnek listesi için bkz: [Trigrafları](../../c-language/trigraphs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)   
 [Trigrafları](../../c-language/trigraphs.md)