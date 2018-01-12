---
title: "Derleyici Hatası C3066 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3066
dev_langs: C++
helpviewer_keywords: C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2303ab6976ff47c73d15cbe68a6b0427d4ba8e6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3066"></a>Derleyici Hatası C3066
Bu tür bir nesne çağrılabilir birden çok yolla bu bağımsız değişken  
  
 Derleyici temsilciler içeren bir belirsiz işlev çağrısı algıladı.  
  
 Aşağıdaki örnek C3066 oluşturur:  
  
```  
// C3066.cpp  
template <class T, class U> void func(T*, U*){}  
  
typedef void (*PF)(const int*, const char*);  
typedef void (*PF1)(const int*, volatile char*);  
  
struct A {  
   operator PF() const {  
      return func;  
   }  
  
   operator PF1() {  
      return func;  
   }  
  
   operator PF1() const  {  
      return func;  
   }  
  
};  
  
int main() {  
   A a;  
   int i;  
   char c;  
  
   a(&i, &c);   // C3066  
   a(&i, (const char *) &c);   // OK  
}  
```

## <a name="copy-list-initialization"></a>Kopya listesi başlatma
Visual Studio 2015'te derleyici yanlışlıkla kopyalama listesi başlatma Normal kopyalama başlatma aynı şekilde ele; yalnızca oluşturucuları aşırı yükleme çözünürlüğü için dönüştürme kabul. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) ancak Visual Studio 2017 doğru hata başlatır seçer.

```
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```