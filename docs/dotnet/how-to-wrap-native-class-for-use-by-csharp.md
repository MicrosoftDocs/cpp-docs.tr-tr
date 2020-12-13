---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: yerel sınıfı C tarafından kullanılmak üzere sarın #'
title: 'Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native code [C++], Visual C# and
- classes [C++], Visual C# and
ms.assetid: 988819ae-cc6a-4453-8ff5-be369210d962
ms.openlocfilehash: 1b90cfba08bd22ec6a49ef4de033afd5d2b187ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151378"
---
# <a name="how-to-wrap-native-class-for-use-by-c"></a>Nasıl yapılır: yerel sınıfı C tarafından kullanılmak üzere sarın\#

Bu örnek, C# veya diğer .NET dilinde yazılmış kod tarafından tüketilebilmesi için yerel C++ sınıfının nasıl sarılacağını gösterir.

## <a name="example"></a>Örnek

```cpp
// wrap_native_class_for_mgd_consumption.cpp
// compile with: /clr /LD
#include <windows.h>
#include <vcclr.h>
#using <System.dll>

using namespace System;

class UnmanagedClass {
public:
   LPCWSTR GetPropertyA() { return 0; }
   void MethodB( LPCWSTR ) {}
};

public ref class ManagedClass {
public:
   // Allocate the native object on the C++ Heap via a constructor
   ManagedClass() : m_Impl( new UnmanagedClass ) {}

   // Deallocate the native object on a destructor
   ~ManagedClass() {
      delete m_Impl;
   }

protected:
   // Deallocate the native object on the finalizer just in case no destructor is called
   !ManagedClass() {
      delete m_Impl;
   }

public:
   property String ^  get_PropertyA {
      String ^ get() {
         return gcnew String( m_Impl->GetPropertyA());
      }
   }

   void MethodB( String ^ theString ) {
      pin_ptr<const WCHAR> str = PtrToStringChars(theString);
      m_Impl->MethodB(str);
   }

private:
   UnmanagedClass * m_Impl;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
