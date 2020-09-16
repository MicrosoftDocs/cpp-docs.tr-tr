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
ms.openlocfilehash: deba9804b9c5c278b3ffcef2923bc8f89fefa676
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684540"
---
# <a name="how-to-declare-handles-in-native-types"></a>Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme

Bir tanıtıcı türünü yerel bir türde bildiremezsiniz. Vcclr. h, `gcroot` C++ YıĞıNıNDAN CLR nesnesine başvurmak için tür açısından güvenli sarmalayıcı şablonu sağlar. Bu şablon, bir sanal tanıtıcıyı yerel bir türe katıştırmanıza ve bunu temel alınan türde gibi değerlendirmenize imkan tanır. Çoğu durumda, `gcroot` nesneyi herhangi bir atama olmadan katıştırılmış tür olarak kullanabilirsiniz. Ancak, [için ' de](../dotnet/for-each-in.md)ile, **`static_cast`** temel alınan yönetilen başvuruyu almak için kullanmanız gerekir.

`gcroot`Şablon, atık toplanan yığına "Handles" sağlayan System:: Runtime:: InteropServices:: GCHandle değer sınıfının işlevleri kullanılarak uygulanır. Tanıtıcıların kendileri atık olarak toplanmadığını ve sınıftaki yok edicinin artık kullanımda olmadığında serbest olduğunu unutmayın `gcroot` (bu yıkıcı el ile çağrılamaz). `gcroot`Yerel yığında bir nesne örneği oluşturursanız, bu kaynakta silme çağrısı yapmanız gerekir.

Çalışma zamanı, tanıtıcı ile başvurduğu CLR nesnesi arasında bir ilişki bakımını koruyacaktır. CLR nesnesi çöp toplanmış yığınla birlikte taşınırsa, tanıtıcı nesnenin yeni adresini döndürür. Bir değişkenin bir şablona atanmadan önce sabitlenmiş olması gerekmez `gcroot` .

## <a name="examples"></a>Örnekler

Bu örnek `gcroot` , yerel yığında bir nesnesinin nasıl oluşturulacağını gösterir.

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

Bu örnek `gcroot` , yerel yığında bir nesnesinin nasıl oluşturulacağını gösterir.

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

Bu örnek `gcroot` `gcroot` , kutulanmış tür üzerinde kullanarak yerel bir türdeki değer türlerine (başvuru türleri değil) başvuruları tutmak için nasıl kullanılacağını gösterir.

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
