---
title: "Derleyici Hatası C2201 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2201
dev_langs: C++
helpviewer_keywords: C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b8874f4ffb4aa0af970f018bceba08e8cbba079
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2201"></a>Derleyici Hatası C2201
'tanımlayıcısı': dış bağlantı dışarı/alınması için olması gerekir  
  
 Dışarı aktarılan tanımlayıcı `static`.  
  
 Aşağıdaki örnek C2286 oluşturur:  
  
```  
// C2201.cpp  
// compile with: /c  
__declspec(dllexport) static void func() {}   // C2201 func() is static  
__declspec(dllexport) void func2() {}   // OK  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı Türleri](../../cpp/types-of-linkage.md)