---
title: "Derleyici Hatası C2272 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa5a23c636b89e3b3c234881a9b2c43d4a288bbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2272"></a>Derleyici Hatası C2272
'function': değiştiricileri statik üye işlevleri izin verilmiyor  
  
 A `static` üye işlevi bildirilen bellek model tanımlayıcısı ile gibi [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md), ve bu tür değiştiricileri izin verilmez `static` üye işlevleri.  
  
 Aşağıdaki örnek C2272 oluşturur:  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```