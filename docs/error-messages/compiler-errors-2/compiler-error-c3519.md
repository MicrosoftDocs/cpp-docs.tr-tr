---
title: "Derleyici Hatası C3519 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3519
dev_langs: C++
helpviewer_keywords: C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c655c8ba0513bcf25d5bc9666d65352a7f587374
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3519"></a>Derleyici Hatası C3519
'invalid_param': embedded_idl özniteliği için geçersiz parametre  
  
 Bir parametre geçildi `embedded_idl` özniteliği [#import](../../preprocessor/hash-import-directive-cpp.md), ancak derleyici parametresi tanımıyor.  
  
 İçin izin verilen tek parametreleri `embedded_idl` olan `emitidl` ve `no_emitidl`.  
  
 Aşağıdaki örnek C3519 oluşturur:  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```