---
title: "Derleyici Hatası C3395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3395
dev_langs: C++
helpviewer_keywords: C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93009d77c40535997ecc42ccb715f5fe81d79798
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3395"></a>Derleyici Hatası C3395
'function': __declspec(dllexport) işlevi ile uygulanamaz \__clrcall çağırma  
  
 `__declspec(dllexport)`ve [__clrcall](../../cpp/clrcall.md) uyumlu değil.  Daha fazla bilgi için bkz: [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
 Aşağıdaki örnek C3395 oluşturur:  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```