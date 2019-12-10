---
title: swap İşlevi (auto_gcroot)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
helpviewer_keywords:
- swap function
ms.assetid: 2fe8146b-a7f7-445a-9ae9-53b5556be701
ms.openlocfilehash: 271ecd26136671737a47b7adbaee273a0997102d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988456"
---
# <a name="swap-function-auto_gcroot"></a>swap İşlevi (auto_gcroot)

Nesneleri bir `auto_gcroot` ve diğeri arasında değiştirir.

## <a name="syntax"></a>Sözdizimi

```
template<typename _element_type>
void swap(
   auto_gcroot<_element_type> & _left,
   auto_gcroot<_element_type> & _right
);
```

#### <a name="parameters"></a>Parametreler

*_left*<br/>
Bir `auto_gcroot`.

*_right*<br/>
Başka bir `auto_gcroot`.

## <a name="example"></a>Örnek

```cpp
// msl_swap_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr \ auto_gcroot. h >

**Ad alanı** msclr

## <a name="see-also"></a>Ayrıca bkz.

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot::swap](../dotnet/auto-gcroot-swap.md)
