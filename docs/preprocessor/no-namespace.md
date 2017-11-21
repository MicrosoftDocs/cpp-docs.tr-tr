---
title: no_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_namespace
dev_langs: C++
helpviewer_keywords: no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb41ec2820468180392a42e8f48684624c7d598d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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