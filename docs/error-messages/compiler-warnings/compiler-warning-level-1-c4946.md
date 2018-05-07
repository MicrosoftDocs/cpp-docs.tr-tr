---
title: Derleyici Uyarısı (düzey 1) C4946 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4946
dev_langs:
- C++
helpviewer_keywords:
- C4946
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 072e43f4750d2f64fb0f9dc56478a68699b98c9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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