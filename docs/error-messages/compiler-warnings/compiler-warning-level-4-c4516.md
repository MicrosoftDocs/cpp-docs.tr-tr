---
title: Derleyici Uyarısı (düzey 4) C4516 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5ca56734d5bd9f2ddf66732ed894d805e368664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4516"></a>Derleyici Uyarısı (düzey 4) C4516
'class::symbol': erişim bildirimleri dışıdır; üye kullanarak bildirimleri daha iyi bir alternatif sunar  
  
 ANSI C++ komitesi erişim bildirimleri belirtmiş (üyesi bir türetilmiş sınıfta erişimini değiştirme [kullanarak](../../cpp/using-declaration.md) anahtar sözcüğü) güncel olması. Erişim bildirimleri C++ gelecekteki sürümleri tarafından desteklenmiyor olabilir.  
  
 Aşağıdaki örnek C4516 oluşturur:  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```