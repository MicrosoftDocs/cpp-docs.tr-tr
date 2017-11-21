---
title: "Bağlayıcı araçları hatası LNK2020 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2020
dev_langs: C++
helpviewer_keywords: LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d9a4bedb06ccad45a105c0e47fbc1f839891bea7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2020"></a>Bağlayıcı Araçları Hatası LNK2020
Çözümlenmemiş belirteci 'belirteci'  
  
 Benzer şekilde tanımlanmamış bir dış hata meta verileri yoluyla başvurudur dışında. Meta verilerde tüm işlevler ve verileri tanımlanması gerekir.  
  
 Çözmek için:  
  
-   Eksik işlev veya veri tanımlayın veya  
  
-   Nesne dosyası ya da eksik işlev veya veri zaten tanımlandığı kitaplığı içerir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK2020 oluşturur.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## <a name="example"></a>Örnek  
 Yönetilen şablon türünde bir değişken oluşturmak, ancak aynı zamanda türü örneği değil LNK2020 da meydana gelir.  
  
 Aşağıdaki örnek LNK2020 oluşturur.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```