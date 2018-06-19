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
ms.openlocfilehash: a8923adb4cf2e92d72bf656064c6de8fc66e2a91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850788"
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