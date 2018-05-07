---
title: Derleyici Hatası C2691 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2691
dev_langs:
- C++
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc6a20aaf3cf9d634d7426b0b7b59f624e184d42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2691"></a>Derleyici Hatası C2691
'veri türü': yönetilen bir ya da WinRTarray bu öğe türüne sahip olamaz  
  
 Yönetilen tür veya WinRT dizi öğesi bir değer türü veya bir başvuru türü olabilir.  
  
 Aşağıdaki örnek C2691 oluşturur:  
  
```  
// C2691a.cpp  
// compile with: /clr  
class A {};  
  
int main() {  
   array<A>^ a1 = gcnew array<A>(20);   // C2691  
   array<int>^ a2 = gcnew array<int>(20);   // value type OK  
}  
```  
