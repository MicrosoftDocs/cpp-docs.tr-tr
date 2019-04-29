---
title: __clrcall
ms.date: 11/04/2016
f1_keywords:
- __clrcall_cpp
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
ms.openlocfilehash: bc44feb97223de47f45734f75777ee040d0ebdd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364577"
---
# <a name="clrcall"></a>__clrcall

**Microsoft'a özgü**

Bir işlev yalnızca yönetilen koddan çağrılabilir belirtir.  Kullanım **__clrcall** yönetilen koddan çağrılan yalnızca tüm sanal işlevler için. Ancak bu çağırma kuralı, yerel koddan çağrılan işlevler için kullanılamaz.

Kullanım **__clrcall** yönetilen bir sanal işlev için yönetilen bir işlevden veya yönetilen bir işlev işaretçisi aracılığıyla yönetilen çalışması çağırırken performansını artırmak için.

Giriş noktaları ayrı, derleyicinin ürettiği işlevlerdir. Bir işlev hem de yerel ve yönetilen giriş noktaları varsa, bunlardan biri işlev uygulaması ile gerçek işlevi olacaktır. Diğer bir işlev PInvoke gerçekleştirmek ortak dil çalışma zamanı sağlar ve gerçek işleve çağrı ayrı bir işleve (dönüştürücü) olacaktır. Bir işlev olarak işaretleme olduğunda **__clrcall**, işlev uygulaması, MSIL olmalıdır ve yerel giriş noktası işlevini oluşturulmaz gösterir.

Yerel bir işlevin adresini almak **__clrcall** belirtilmezse, derleyici yerel giriş noktasını kullanır. **__clrcall** işlevi yönetilir ve geçiş adımlarını gerek yönetilen yerel olduğunu gösterir. Bu durumda derleyici yönetilen giriş noktasını kullanır.

Zaman `/clr` (değil `/clr:pure` veya `/clr:safe`) kullanılır ve **__clrcall** olan kullanılmaz, bir işlevin adresini her zaman ayırdığınız yerel giriş noktası işlevini adresini döndürür. Zaman **__clrcall** olduğu değil giriş noktası dönüştürücü işlevini yönetilen işlevin adresini almak için kullanıldığında, yerel giriş noktası işlevini oluşturulmaz. Daha fazla bilgi için [çift dönüştürme](../dotnet/double-thunking-cpp.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

[/ CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) tüm işlevleri ve işlev işaretçileri olduğunu ima **__clrcall** ve derleyici dışındaherşeyişaretlenecekderlenecekbirişlevdeizinverilmiyor **__clrcall**. Zaman **/CLR: pure** kullanılan **__clrcall** yalnızca işlev işaretçileri ve dış bildirimler belirtilebilir.

Doğrudan Çağırabilir miyim **__clrcall** mevcut işlevleri C++ kullanarak derlenen kod **/CLR** bu işlevin MSIL uygulamaya sahip olduğu sürece. **__clrcall** işlevleri bile bu işlevleri ile derlenmiş doğrudan satır içi asm ve CPU özgü intrinisics gibi arama işlevleri çağrılamaz `/clr`.

**__clrcall** işlev işaretçileri yalnızca içinde oluşturuldukları uygulama etki alanında kullanılmak üzere geliyordu.  Yerine geçme **__clrcall** kullanmak, uygulama etki alanları arasında işlev işaretçileri <xref:System.CrossAppDomainDelegate>. Daha fazla bilgi için [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Örnek

İle bildirilen bir işlevi unutmayın **__clrcall**, kod gerektiğinde oluşturulur; Örneğin, ne zaman işlevi çağrılır.

```cpp
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

Yönetilen koddan yalnızca çağrılacak işlev işaretçisi bildirme gibi aşağıdaki örnek, bir işlev işaretçisi tanımlayabilirsiniz gösterir. Bu, derleyicinin doğrudan yönetilen işlevi çağırabilir ve yerel giriş noktası (çift dönüştürücü sorun) önlemek sağlar.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
