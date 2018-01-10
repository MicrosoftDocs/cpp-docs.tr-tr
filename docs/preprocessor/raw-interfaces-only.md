---
title: raw_interfaces_only | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_interfaces_only
dev_langs: C++
helpviewer_keywords: raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d7790601a3eec16cae67542ac2d8d622b71df2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)