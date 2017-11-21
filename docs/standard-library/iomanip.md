---
title: '&lt;iomanip&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::<iomanip>
- <iomanip>
dev_langs: C++
helpviewer_keywords: iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8476743513fa4373b267af3891c59680d2657cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;
Dahil `iostreams` standart üstbilgi `<iomanip>` , her birkaç manipülatörleri tanımlamak için tek bir bağımsız değişken alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <iomanip>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her bu manipülatörleri adlı belirtilmeyen bir türü döndürür **T1** aracılığıyla **T10**, her ikisi de overloads `basic_istream` \< **Elem**, **Tr**>`::`[işleci >>](../standard-library/istream-operators.md#op_gt_gt) ve `basic_ostream` \< **Elem**, **Tr** > `::` [işleci <<](../standard-library/ostream-operators.md#op_lt_lt).  
  
### <a name="manipulators"></a>Manipülatörleri  
  
|||  
|-|-|  
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Uluslararası biçiminde isteğe bağlı olarak bir para miktarını alır.|  
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Belirtilen biçimi kullanarak bir zaman yapısı bir sürede alır.|  
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Uluslararası biçiminde isteğe bağlı olarak, parasal bir tutar sağlar.|  
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Zaman yapısı ve kullanmak için bir biçim dizesi zamanında sağlar.|  
|[tırnak içine alınmış](../standard-library/iomanip-functions.md#quoted)|Dizeler ekleme ve çıkarma işleçleri ile uygun gidiş sağlar.|  
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Belirtilen bayrakları temizler.|  
|[setbase](../standard-library/iomanip-functions.md#setbase)|Tamsayıları için temel olarak ayarlayın.|  
|[setfill](../standard-library/iomanip-functions.md#setfill)|Sağa hizalı görüntü alanları doldurmak için kullanılan karakter ayarlar.|  
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Belirtilen bayrakları ayarlar.|  
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Kayan nokta değerlerinin duyarlık ayarlar.|  
|[setw](../standard-library/iomanip-functions.md#setw)|Görüntü alanı genişliğini belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)



