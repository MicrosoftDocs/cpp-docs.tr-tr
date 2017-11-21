---
title: "Derleyici Hatası C2059 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2059
dev_langs: C++
helpviewer_keywords: C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbf80ab803eaaacc29ac82657af130194417f1c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2059"></a>Derleyici Hatası C2059
sözdizimi hatası: 'belirteci'  
  
 Belirtecin bir sözdizimi hatası nedeniyle.  
  
 Aşağıdaki örnek bildiren bir satır için bir hata iletisi oluşturur `j`.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 Hatanın nedenini belirlemek için yalnızca hata iletisinde listelenen satır, aynı zamanda üstündeki satırları inceleyin. Satırları incelenerek sorun ilgili hiçbir ipucu döndürürse, hata iletisinde listelenen satır ve belki de birkaç satır üzerindeki yorum oluşturmayı deneyin.  
  
 Hata iletisi hemen izleyen bir sembol oluşursa bir `typedef` değişkeni, değişken kaynak kodunda tanımlandığından emin olun.  
  
 Bir simge oluşabilir gibi nothing olarak değerlendirilirse C2059 alabilirsiniz zaman **/D** `symbol`  **=**  derlemek için kullanılır.  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 Varsayılan bağımsız değişkenler işlevi için bir yapı belirten bir uygulamayı derlediğinizde C2059 oluşabilen başka bir durumdur. Bağımsız değişken için varsayılan değeri bir ifade olmalıdır. Başlatıcı listesi — Örneğin, bir bir yapı başlatmak için kullanılan — bir ifade değil.  Bu sorunu çözmek için gerekli başlatılmasını gerçekleştirmek için bir oluşturucu tanımlayın.  
  
 Aşağıdaki örnek C2059 oluşturur:  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 Üye Şablon sınıfı veya sınıfın dışından işlevi tanımlarsanız C2059 elde edebilirsiniz. Bilgi için bkz: [Bilgi Bankası makalesi 241949](http://support.microsoft.com/kb/241949).  
  
 C2059 hatalı oluşturulmuş bir atama için oluşabilir.  
  
 Aşağıdaki örnek C2059 oluşturur:  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 Nokta içeren bir ad alanı adı oluşturmayı denerseniz, C2059 da oluşabilir.  
  
 Aşağıdaki örnek C2059 oluşturur:  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 bir adını nitelemek bir işleç olduğunda meydana gelebilir (`::`, `->`, ve `.`) anahtar sözcüğü tarafından uyulması gereken `template`, bu örnekte gösterildiği gibi:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 Varsayılan olarak, C++ varsayar `AY::Rebind` olmayan bir şablon; bu nedenle, aşağıdaki `<` daha az yorumlanır-oturum daha.  Derleyici açıkça, size gereken `Rebind` açılı ayraç doğru ayrıştıramıyor böylece bir şablondur. Bu hatayı düzeltmek için kullanmak `template` anahtar sözcüğü aşağıda gösterildiği gibi bağımlı tür adı:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```