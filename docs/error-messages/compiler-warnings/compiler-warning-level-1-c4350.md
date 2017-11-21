---
title: "Derleyici Uyarısı (düzey 1) C4350 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4350
dev_langs: C++
helpviewer_keywords: C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5484c1cb82230eb2bb26004af8a81dcdde1177e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4350"></a>Derleyici Uyarısı (düzey 1) C4350
behavior change: 'member2' yerine 'member1' çağrıldı  
  
 Bir rvalue const olmayan başvuru bağlanamaz. Visual Studio 2003 önce Visual C++ sürümlerinde, bir rvalue doğrudan başlatma const olmayan başvuru bağlamak mümkündü. Bu kod, artık bir uyarı verir.  
  
 Geriye dönük uyumluluk için sabit olmayan başvurular rvalues bağlamak hala mümkündür, ancak standart dönüşümler mümkün olduğunda tercih edilir.  
  
 Bu uyarı, Visual C++ .NET 2002 derleyiciden davranış değişikliği temsil eder. Bu uyarı, büyük olasılıkla etkinleştirilirse, doğru kodunu belirtilen. Örneğin, bunu kullanırken verilmesi **std::auto_ptr** sınıf şablonu.  
  
 Bu uyarıyı alırsanız, bağlama rvalues const olmayan başvuruları yapılandırmasanız görmek için kodunuzu inceleyin. Bir const başvuru ekleyerek veya ek bir const başvuru aşırı sağlama sorunu çözebilir.  
  
 Varsayılan olarak bu uyarı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Aşağıdaki örnek C4350 oluşturur:  
  
```cpp  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead:  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```