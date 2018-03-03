---
title: "Derleyici Uyarısı (düzey 1) C4273 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4273
dev_langs:
- C++
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36301a4447d309c4673006d3dfd52f86b031f251
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4273"></a>Derleyici Uyarısı (düzey 1) C4273
'function': tutarsız DLL bağlantı  
  
 Bir dosyada iki tanımları, kendi kullanımda farklı [dllimport](../../cpp/dllexport-dllimport.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4273 oluşturur.  
  
```  
// C4273.cpp  
// compile with: /W1 /c  
char __declspec(dllimport) c;  
char c;   // C4273, delete this line or the line above to resolve  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4273 oluşturur.  
  
```  
// C4273_b.cpp  
// compile with: /W1 /clr /c  
#include <stdio.h>  
extern "C" int printf_s(const char *, ...);   // C4273  
```