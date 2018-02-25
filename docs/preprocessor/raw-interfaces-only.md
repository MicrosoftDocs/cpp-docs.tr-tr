---
title: raw_interfaces_only | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eff60ded57ae66b43dee4b3b95699ad498fa0358
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++ özel**  
  
 Hata işleme sarmalayıcı işlevleri oluşturulmasını önler ve [özelliği](../cpp/property-cpp.md) bu sarmalayıcı işlevleri kullanmak bildirimleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `raw_interfaces_only` Özniteliği de kaldırılacak özelliği olmayan işlevleri adlandırma kullanılan varsayılan önek neden olur. Normalde, önektir **raw_**. Bu öznitelik belirtilirse, işlevi doğrudan tür kitaplığından adlardır.  
  
 Bu öznitelik, yalnızca alt düzey içeriği tür kitaplığı kullanıma olanak tanır.  
  
 Son C++ özel  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)