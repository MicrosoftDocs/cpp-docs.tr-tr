---
title: Derleyici Uyarısı (düzey 4) C4626 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4626
dev_langs:
- C++
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e43aa93a2f40d97ef3db5c2f556b04e84512724
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4626"></a>Derleyici Uyarısı (düzey 4) C4626
'türetilmiş bir sınıf': atama işleci bir temel sınıf atama işleci erişilemez veya silinmiş olduğundan silindi olarak örtük olarak tanımlanmıştı  
  
 Atama işleci silinmiş ya da bir taban sınıf içinde erişilebilir değil ve bu nedenle türetilmiş bir sınıf için oluşturulmamış. Bu tür nesneler atama denemesi herhangi bir derleyici hatası neden olur.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4626 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C4626  
// compile with: /W4  
#pragma warning(default : 4626)  
class B  
{  
// public:  
   B& operator = (const B&)  
   {  
      return *this;  
   }  
};  
  
class D : public B  
{  
  
}; // C4626 - to fix, make B's copy constructor public  
  
int main()  
{  
   D m;  
   D n;  
   // m = n;   // this line will cause an error  
}  
```