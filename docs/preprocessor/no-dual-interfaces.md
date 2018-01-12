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
ms.workload: cplusplus
ms.openlocfilehash: 42501c329b5c040f762b692e9298b184a2035d7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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