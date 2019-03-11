---
title: 'Nasıl yapılır: Yönetilmeyen bellekte nesne başvurusunu tutun'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 0d8dc341d1fe2c61eba098abec9258a2c6dade79
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747988"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Nasıl yapılır: Yönetilmeyen bellekte nesne başvurusunu tutun

Saran gcroot.h kullanabileceğiniz <xref:System.Runtime.InteropServices.GCHandle>, yönetilmeyen bellekte bir CLR nesne başvurusu tutacak. Alternatif olarak, `GCHandle` doğrudan.

## <a name="example"></a>Örnek

```
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

## <a name="example"></a>Örnek

`GCHandle` size bir yönetilen nesne başvurusu yönetilmeyen bellekte tutmak için bir yol sağlar.  Kullandığınız <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> yönetilen bir nesne için donuk bir tanıtıcı yöntemini ve <xref:System.Runtime.InteropServices.GCHandle.Free%2A> bunu serbest bırakmak için. Ayrıca, <xref:System.Runtime.InteropServices.GCHandle.Target%2A> yöntemi yönetilen kodda tanıtıcı nesne başvurusu geri almak sağlar.

```
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
