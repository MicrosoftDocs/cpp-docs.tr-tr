---
title: raw_interfaces_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4643181bf70bc92f4ef5e88b8a9add1ba7bdaad7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849307"
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