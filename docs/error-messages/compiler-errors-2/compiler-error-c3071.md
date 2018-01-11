---
title: "Derleyici Hatası C3071 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3071
dev_langs: C++
helpviewer_keywords: C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dfe7bf24ac7b81387420a52cfb9f39989fe43b68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3071"></a>Derleyici Hatası C3071
operator 'işleci' ref sınıfı ya da bir değer türü örneği için yalnızca uygulanabilir  
  
 Bir CLR işleci bir yerel türünde kullanılamaz. İşleç ref sınıfı veya ref yapı (bir değer türü) ancak int veya bir diğer ad gibi yerel bir türde System::Int32 gibi yerel bir tür için kullanılabilir. Bu tür işleci kullanılamaz, yerel bir değişkene göndermede şekilde C++ kodundan Kutulu olamaz.  
  
 Daha fazla bilgi için bkz: [izleme başvurusu işleci](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3071 oluşturur.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```