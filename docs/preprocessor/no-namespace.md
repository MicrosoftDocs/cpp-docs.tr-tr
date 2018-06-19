---
title: no_namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d4558b0fd6a4014bc9601d5260882af444f87e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912751"
---
# <a name="nonamespace"></a>no_namespace
**C++ özel**  
  
 Ad alanı adı derleyici tarafından oluşturulmayan belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tür kitaplığı içeriği `#import` üstbilgi dosyası normalde bir ad alanında tanımlı. Ad alanı adı belirtilen **Kitaplığı** özgün IDL dosyasının deyimi. Varsa `no_namespace` özniteliği belirtilmediyse, ardından bu ad alanı derleyici tarafından oluşturulmaz.  
  
 Farklı bir ad kullanmak istiyorsanız, daha sonra kullanmak [rename_namespace](../preprocessor/rename-namespace.md) yerine özniteliği.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)