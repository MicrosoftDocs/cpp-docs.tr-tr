---
title: auto_gcroot::swap
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr.auto_gcroot.swap
- msclr::auto_gcroot::swap
- auto_gcroot::swap
- auto_gcroot.swap
helpviewer_keywords:
- auto_gcroot::swap
ms.assetid: 4915c629-6a53-432c-8155-3a7511dc70cb
ms.openlocfilehash: 8c968a12e3486715b3c91a7c12c4fc366d6fb5bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552106"
---
# <a name="autogcrootswap"></a>auto_gcroot::swap

Başka bir nesneyle değiştirir `auto_gcroot`.

## <a name="syntax"></a>Sözdizimi

```
void swap(
   auto_gcroot<_element_type> & _right
);
```

#### <a name="parameters"></a>Parametreler

*_right*<br/>
`auto_gcroot` Hangi ile takas nesneleri.

## <a name="example"></a>Örnek

```
// msl_auto_gcroot_swap.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   s1.swap( s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[auto_gcroot Members](../dotnet/auto-gcroot-members.md)<br/>
[swap Function (auto_gcroot)](../dotnet/swap-function-auto-gcroot.md)