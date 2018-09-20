---
title: 'Nasıl yapılır: yerel türlerde işleyicileri bildirme | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
f1_keywords:
- gcroot
dev_langs:
- C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fbf2934c2d7a1192e55ee9b454f91e7e8cc7037f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431274"
---
# <a name="how-to-declare-handles-in-native-types"></a>Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme

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

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)