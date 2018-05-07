---
title: Derleyici Uyarısı (düzey 4) C4625 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4625
dev_langs:
- C++
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9279d5a9bfa7aa80ae866d290624f1edf888e36b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4625"></a>Derleyici Uyarısı (düzey 4) C4625
'türetilmiş bir sınıf': kopya oluşturucu temel sınıf kopya Oluşturucu erişilemez veya silinmiş olduğundan silindi olarak örtük olarak tanımlanmıştı  
  
 Kopya Oluşturucu silinmiş ya da bir taban sınıf içinde erişilebilir değil ve bu nedenle türetilmiş bir sınıf için oluşturulmamış. Bu türdeki bir nesneyi kopyalamak için her türlü girişim derleyici hatası neden olur.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4625 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C4625.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4625)  
  
struct A {  
   A() {}  
  
private:  
   A(const A&) {}  
};  
  
struct C : private virtual A {};  
struct B :  C {};   // C4625 no copy constructor  
  
struct D : A {};  
struct E :  D {};   // OK  
```