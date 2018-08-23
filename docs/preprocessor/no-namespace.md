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
ms.openlocfilehash: 6eded6b4d543248cc7bf53a0e4ba622b2b74c8b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464861"
---
# <a name="nonamespace"></a>no_namespace
**C++ özgü**  
  
Ad alanı adı derleyici tarafından oluşturulmayan belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Tür kitaplığı içeriğini içinde `#import` üstbilgi dosyası normalde bir ad alanında tanımlı. Ad alanı adı belirtilen `library` özgün IDL dosyası ifadesi. Varsa **no_namespace** özniteliği belirtilmediyse, sonra bu ad alanı, derleyici tarafından oluşturulmaz.  
  
Farklı bir ad kullanmak istiyorsanız, ardından kullanmak [rename_namespace](../preprocessor/rename-namespace.md) yerine özniteliği.  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)