---
title: 'Nasıl yapılır: Yerel türlerde işleyicileri bildirme'
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: f5d6d31be9f3c10e1a56639ccf20663ce59d7941
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387415"
---
# <a name="how-to-declare-handles-in-native-types"></a>Nasıl yapılır: Yerel türlerde işleyicileri bildirme

Bir yerel tür içinde tanıtıcı türüne bildiremezsiniz. tür kullanımı uyumlu sarmalayıcı şablon Vcclr.h sağlar `gcroot` C++ yığınından bir CLR nesnesine başvurmak için. Bu şablon, sanal bir tanıtıcı yerel bir tür ekleme ve temel alınan türü değilmiş gibi ele almanız sağlar. Çoğu durumda, kullandığınız `gcroot` herhangi bir atama olmadan katıştırılmış tür olarak nesnesi. Bununla birlikte, [her, içinde](../dotnet/for-each-in.md), kullanmak zorunda `static_cast` temel yönetilen başvuru alınamıyor.

`gcroot` Şablonu, atık olarak toplanmış yığınla "işler" sağlayan System::Runtime değer sınıfının özellikleri kullanılarak gerçekleştirilir. Tanıtıcıları çöp olarak toplanacak olmadığına dikkat edin ve artık kullanımda olmadığında yıkıcı tarafından serbest bırakılan `gcroot` sınıfı (Bu yok edici el ile çağrılamaz). Örneği, bir `gcroot` nesne yerel yığında çağırmanız gerekir, bu kaynağa silin.

Çalışma zamanı tanıtıcısı başvurduğu CLR nesne arasındaki ilişkiyi barındırır. Tanıtıcı CLR nesnesi atık olarak toplanmış yığınla geçtiğinde, yeni nesnenin adresini döndürür. Bir değişken için atanmadan önce sabitlenmiş gerekmez bir `gcroot` şablonu.

## <a name="example"></a>Örnek

Bu örnek nasıl oluşturulacağını gösterir. bir `gcroot` nesne yerel yığında.

```
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

Bu örnek nasıl oluşturulacağını gösterir. bir `gcroot` nesne yerel yığında.

```
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

Bu örnek nasıl kullanılacağını gösterir `gcroot` kullanarak yerel bir tür içinde değer türleri (başvuru türleri değil) başvurular tutacak `gcroot` Kutulu türü.

```
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
