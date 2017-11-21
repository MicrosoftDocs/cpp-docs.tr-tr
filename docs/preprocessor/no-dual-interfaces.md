---
title: no_dual_interfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_dual_interfaces
dev_langs: C++
helpviewer_keywords: no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 03118b3f47111364e8d614f101977851891a53ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ özel**  
  
 Değişiklikleri derleyici yolu çift arabirim yöntemleri için sarmalayıcı işlevleri oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sarmalayıcı normalde, arabirim için sanal işlev tablosu aracılığıyla yöntemi çağırır. İle `no_dual_interfaces`, bunun yerine sarmalayıcı çağırır **IDispatch::Invoke** yöntemini çağırmak için.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)