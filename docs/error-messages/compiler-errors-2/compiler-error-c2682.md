---
title: Derleyici Hatası C2682 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2682
dev_langs:
- C++
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9422dc079891e6536c825538c99f4179f2c086c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234087"
---
# <a name="compiler-error-c2682"></a>Derleyici Hatası C2682
'type1' 'type2' dönüştürmek için casting_operator kullanamazsınız  
  
 Atama işleci uyumsuz türleri arasında dönüştürme yapılmaya çalışıldı. Örneğin, kullanamazsınız [dynamic_cast](../../cpp/dynamic-cast-operator.md) bir işaretçi başvuru dönüştürmek için işleci. `dynamic_cast` İşleci, hemen niteleyicileri dönüştürmek için kullanılamaz. Tüm niteleyicileri türleriyle aynı olmalıdır.  
  
 Kullanabileceğiniz `const_cast` öznitelikleri gibi kaldırmak için işleci `const`, `volatile`, veya `__unaligned`.  
  
 Aşağıdaki örnek C2682 oluşturur:  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 Aşağıdaki örnek C2682 oluşturur:  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```