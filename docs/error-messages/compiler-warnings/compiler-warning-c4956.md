---
title: "Derleyici Uyarısı C4956 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4956
dev_langs: C++
helpviewer_keywords: C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cda1c616eabbbbd2972f9d60f6d140758103aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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