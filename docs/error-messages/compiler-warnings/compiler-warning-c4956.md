---
title: Derleyici Uyarısı C4956 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac369ab3bbdd4afdfb5e8aa555770564f54732de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4956"></a>Derleyici Uyarısı C4956
'type': Bu tür doğrulanabilen değil  
  
 Bu uyarı oluşturulduğu zaman [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) belirtilir ve kodunuzu doğrulanabilen değil bir türü içeriyor.  
  
 Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Bu uyarıyı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.  
  
 Aşağıdaki örnek C4956 oluşturur:  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```