---
title: rename_namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51114787dde2f858a8409538083282ef292d599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)