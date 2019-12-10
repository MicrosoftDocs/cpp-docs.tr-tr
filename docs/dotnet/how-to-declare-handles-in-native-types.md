---
title: 'Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme'
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: 11dbc196a89a224afe02312fbe4dff99d8467f4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988241"
---
# <a name="how-to-declare-handles-in-native-types"></a>Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme

Bir tanıtıcı türünü yerel bir türde bildiremezsiniz. Vcclr. h, C++ YıĞıNDA bir CLR nesnesine başvurmak için tür açısından güvenli sarmalayıcı şablonu `gcroot` sağlar. Bu şablon, bir sanal tanıtıcıyı yerel bir türe katıştırmanıza ve bunu temel alınan türde gibi değerlendirmenize imkan tanır. Çoğu durumda, `gcroot` nesnesini katıştırılmış tür olarak herhangi bir atama olmadan kullanabilirsiniz. Bununla birlikte, [her biri için](../dotnet/for-each-in.md)ile, temel alınan yönetilen başvuruyu almak için `static_cast` kullanmanız gerekir.

`gcroot` şablonu, atık olarak toplanmış yığına "Handles" sağlayan System:: Runtime:: InteropServices:: GCHandle değer sınıfının işlevleri kullanılarak uygulanır. Tanıtıcıların kendileri atık olarak toplanmadığını ve artık `gcroot` sınıfında yok edicisi tarafından kullanımda olmadığında serbest olduğunu unutmayın (bu yıkıcı el ile çağrılamaz). Yerel yığında bir `gcroot` nesnesi örneği oluşturursanız, bu kaynakta silme çağrısı yapmanız gerekir.

Çalışma zamanı, tanıtıcı ile başvurduğu CLR nesnesi arasında bir ilişki bakımını koruyacaktır. CLR nesnesi çöp toplanmış yığınla birlikte taşınırsa, tanıtıcı nesnenin yeni adresini döndürür. Bir değişkenin bir `gcroot` şablonuna atanmadan önce sabitlenmiş olması gerekmez.

## <a name="example"></a>Örnek

Bu örnek, yerel yığında bir `gcroot` nesnesinin nasıl oluşturulacağını gösterir.

```cpp
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>Örnek

Bu örnek, yerel yığında bir `gcroot` nesnesinin nasıl oluşturulacağını gösterir.

```cpp
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>Örnek

Bu örnek, paketlenmiş türde `gcroot` kullanarak yerel bir türdeki değer türlerine (başvuru türleri değil) başvuruları tutmak için `gcroot` nasıl kullanacağınızı gösterir.

```cpp
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
