---
title: Derleyici Hatası C2270 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2270
dev_langs:
- C++
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bbafbf35f2aed6d6bddc3298ecfe0e1bf9912e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2270"></a>Derleyici Hatası C2270
'function': değiştiricileri dahil olmayan işlevlere izin verilmiyor  
  
 Dahil olmayan işlevi ile bildirilmiş [const](../../cpp/const-cpp.md), [volatile](../../cpp/volatile-cpp.md), ya da başka bir bellek modeli değiştiricisi.  
  
 Aşağıdaki örnek C2270 oluşturur:  
  
```  
// C2270.cpp  
// compile with: /c  
void func1(void) const;   // C2270, nonmember function  
  
void func2(void);  
  
class CMyClass {  
public:  
   void func2(void) const;  
};  
```