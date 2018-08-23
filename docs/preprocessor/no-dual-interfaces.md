---
title: no_dual_interfaces | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1e919e48b79c9fe98a7a33257ebd0f70061d788
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465235"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ özgü**  
  
Değişiklikleri derleyici yolu çift arabirim yöntemleri için sarmalayıcı işlevleri oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Normalde, sarmalayıcı yöntemin sanal işlev tablosu aracılığıyla arabirimi çağırır. İle **no_dual_interfaces**, bunun yerine sarmalayıcıyı çağıran `IDispatch::Invoke` yöntemini çağırmak için.  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)