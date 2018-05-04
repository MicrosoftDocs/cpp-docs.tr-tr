---
title: __clrcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __clrcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02af89a99b78ba17e6c5a7463073d314ee8d2a03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="clrcall"></a>__clrcall
**Microsoft özel**  
  
 Bir işlev yalnızca yönetilen koddan çağrılabilir belirtir.  Kullanım `__clrcall` yönetilen koddan çağrılan yalnızca tüm sanal işlev. Ancak bu çağırma yerel koddan çağrılan işlevler için kullanılamaz.  
  
 Kullanım `__clrcall` yönetilen bir sanal işlev yönetilen bir işleve veya yönetilen işlev işaretçisi aracılığıyla yönetilen çalışması çağrılırken performansını artırmak için.  
  
 Giriş noktaları ayrı, derleyicinin ürettiği işlevlerdir. Bir işlev hem yerel ve yönetilen giriş noktaları varsa, bunlardan birini işlevi uygulamasıyla gerçek işlevi olacaktır. Diğer işlevi gerçek işlevi çağırır ve PInvoke gerçekleştirmek ortak dil çalışma zamanı sağlar ayrı bir işleve (dönüştürücü) olacaktır. Bir işlevi olarak işaretleme zaman `__clrcall`, işlev uygulaması MSIL olmalıdır ve yerel giriş noktası işlevi oluşturulmayacak gösterir.  
  
 Yerel bir işleve adresini varsa alırken `__clrcall` belirtilmezse, derleyici, yerel giriş noktası kullanır. `__clrcall` Yönetilen işlevi ve geçiş gitmesi gerekli çok yerel yönetilen olduğunu gösterir. Bu durumda derleyici yönetilen giriş noktasını kullanır.  
  
 Zaman **/CLR** (değil **/CLR: pure** veya **/CLR: safe**) kullanılır ve `__clrcall` olduğu kullanılmaz, bir işlev adresi her zaman ayırdığınız yerel giriş adresini döndürür işlev gelin. Zaman `__clrcall` olan bir giriş noktası dönüştürücü çalışmamasına yönetilen işlevinin adresini almak için kullanıldığında, yerel giriş noktası işlevi oluşturulmaz. Daha fazla bilgi için bkz: [çift dönüştürme](../dotnet/double-thunking-cpp.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 [/ CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) tüm işlevler ve işlev işaretçileri olduğunu gelir `__clrcall` ve derleyici hiçbir şey dışında işaretlenmesi derlenecek işlevinde izin değil `__clrcall`. Zaman **/CLR: pure** kullanılan `__clrcall` yalnızca işlev işaretçileri ve dış bildirimler belirtilebilir.  
  
 Doğrudan Çağırabilir miyim `__clrcall` kullanarak derlenen mevcut C++ kodunu işlevlerden **/CLR** MSIL uygulaması bu işleve sahip olduğu sürece. `__clrcall` İşlevler ile derlenmiş bu işlevler olsa bile doğrudan satır içi asm ve CPU özgü intrinisics, örneğin, arama işlevleri çağrılamaz **/CLR**.  
  
 `__clrcall` işlev işaretçileri yalnızca bunlar oluşturulduğu uygulama etki alanında kullanılacak yöneliktir.  Yerine geçme `__clrcall` işlev işaretçileri uygulama etki alanlarında, kullanmak <xref:System.CrossAppDomainDelegate>. Daha fazla bilgi için bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Örnek  
 Bir işlev ile bildirildiğinde unutmayın `__clrcall`, gerektiğinde kod oluşturulacak; Örneğin, ne zaman işlevi çağrılır.  
  
```  
// clrcall2.cpp  
// compile with: /clr  
using namespace System;  
int __clrcall Func1() {  
   Console::WriteLine("in Func1");  
   return 0;  
}  
  
// Func1 hasn't been used at this point (code has not been generated),   
// so runtime returns the adddress of a stub to the function  
int (__clrcall *pf)() = &Func1;  
  
// code calls the function, code generated at difference address  
int i = pf();   // comment this line and comparison will pass  
  
int main() {  
   if (&Func1 == pf)  
      Console::WriteLine("&Func1 == pf, comparison succeeds");  
   else   
      Console::WriteLine("&Func1 != pf, comparison fails");  
  
   // even though comparison fails, stub and function call are correct  
   pf();  
   Func1();  
}  
```  
  
```Output  
in Func1  
&Func1 != pf, comparison fails  
in Func1  
in Func1  
```  
  
## <a name="example"></a>Örnek  
 Yönetilen koddan yalnızca çağrılacak işlev işaretçisi bildirme sağlayacak şekilde, aşağıdaki örnek, bir işlev işaretçisi tanımlayabilirsiniz gösterir. Bu, doğrudan yönetilen işlevini çağırın ve yerel giriş noktası (çift dönüştürücü sorun) önlemek derleyici sağlar.  
  
```  
// clrcall3.cpp  
// compile with: /clr  
void Test() {  
   System::Console::WriteLine("in Test");  
}  
  
int main() {  
   void (*pTest)() = &Test;  
   (*pTest)();  
  
   void (__clrcall *pTest2)() = &Test;  
   (*pTest2)();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)