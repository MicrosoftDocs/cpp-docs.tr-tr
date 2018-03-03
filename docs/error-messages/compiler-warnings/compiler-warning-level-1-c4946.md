---
title: "Derleyici Uyarısı (düzey 1) C4946 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4946
dev_langs:
- C++
helpviewer_keywords:
- C4946
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 800d940c3005762bddf6402a14af4416da4bc50e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4946"></a>Derleyici Uyarısı (düzey 1) C4946
reinterpret_cast ilgili sınıflar arasında kullanıldı: 'class1' ve 'class2'  
  
 Kullanmayın [reinterpret_cast](../../cpp/reinterpret-cast-operator.md) ilgili türleri arasında yayınlanamıyor. Kullanmak [static_cast](../../cpp/static-cast-operator.md) bunun yerine veya çok biçimli türleri için kullanmak [dynamic_cast](../../cpp/dynamic-cast-operator.md).  
  
 Varsayılan olarak, bu uyarıyı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Aşağıdaki kod örneğinde C4946 oluşturur:  
  
```  
// C4946.cpp  
// compile with: /W1  
#pragma warning (default : 4946)  
class a {  
public:  
   a() : m(0) {}  
   int m;  
};  
  
class b : public virtual a {  
};  
  
class b2 : public virtual a {  
};  
  
class c : public b, public b2 {  
};  
  
int main() {  
   c* pC = new c;  
   a* pA = reinterpret_cast<a*>(pC);   // C4946  
   // try the following line instead  
   // a* pA = static_cast<a*>(pC);  
}  
```