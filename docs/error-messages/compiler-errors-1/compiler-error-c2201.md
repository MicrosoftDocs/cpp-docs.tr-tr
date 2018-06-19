---
title: Derleyici Hatası C2201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2201
dev_langs:
- C++
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eea410297cdb8deb45c4376f8736234ad8f69699
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170836"
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