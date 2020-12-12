---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: yönetilmeyen bellekte nesne başvurusunu tutma'
title: 'Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 9c54d0ce376e57c5865c2fef5987d878bfa8d7f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134933"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma

<xref:System.Runtime.InteropServices.GCHandle>Yönetilmeyen bellekte BIR CLR nesne başvurusunu tutmak için, sarmalanmış olan gcroot. h ' yi kullanabilirsiniz. Alternatif olarak, doğrudan kullanabilirsiniz `GCHandle` .

## <a name="examples"></a>Örnekler

```cpp
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

`GCHandle` yönetilmeyen bellekte yönetilen bir nesne başvurusunu tutmak için bir yol sağlar.  <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A>Yöntemi, yönetilen bir nesne için donuk bir tanıtıcı oluşturmak ve onu serbest bırakmak için kullanın <xref:System.Runtime.InteropServices.GCHandle.Free%2A> . Ayrıca, <xref:System.Runtime.InteropServices.GCHandle.Target%2A> yöntemi Yönetilen koddaki işleyicinizden nesne başvurusunu elde etmenizi sağlar.

```cpp
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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
