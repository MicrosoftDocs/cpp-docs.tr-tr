---
title: embedded_idl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0b594952e8e5be0a9be9c843877c8c4bb95eca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="embeddedidl"></a>embedded_idl
**C++ özel**  
  
 Tür kitaplığı, öznitelik oluşturulan kod korunur .tlh dosyasına yazılır belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
embedded_idl[("param")]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `param`  
 İki değerden biri olabilir:  
  
-   emitidl: Tür Kitaplığı ' alınan tür bilgileri öznitelikli projesi için oluşturulan IDL de mevcut olacaktır.  Bu varsayılandır ve parametresi belirtmezseniz uygulanmaz `embedded_idl`.  
  
-   no_emitidl: Tür Kitaplığı ' alınan tür bilgileri öznitelikli projesi için oluşturulan IDL mevcut olmaz.  
  
## <a name="example"></a>Örnek  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)