---
title: rename_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="renamenamespace"></a>rename_namespace
**C++ özel**  
  
 Tür kitaplığı içeriğini içeren ad alanını yeniden adlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `NewName`  
 Yeni ad alanı adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Tek bir bağımsız değişken alan *NewName*, ad alanı için yeni bir ad belirtir.  
  
 Ad alanını kaldırmak için kullanın [no_namespace](../preprocessor/no-namespace.md) yerine özniteliği.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)