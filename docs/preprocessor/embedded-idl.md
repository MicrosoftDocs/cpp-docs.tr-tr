---
title: embedded_idl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8a93f71da7b7f0819b5a48af1541909037bbe65
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)